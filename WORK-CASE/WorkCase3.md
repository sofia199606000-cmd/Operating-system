# ЗВІТ

## з виконання WORK-CASE №3

**Тема:** Клонування віртуальних машин та налаштування мережевої взаємодії у середовищах віртуалізації.

**Виконали:**

Студентки групи **БІКС-33**
* Вітер Софія Володимирівна
* Данченко Ксенія Олегівна

---

## Словник англійських термінів

**Virtual Machine (VM) / Віртуальна машина — програмна емуляція реального комп'ютера, на якій можна встановити окрему операційну систему (Linux) всередині вашої основної (Windows).**

**Cloning / Клонування — процес створення ідентичної копії вже налаштованої віртуальної машини зі всіма її файлами та програмам**

**Snapshot / Знімок стану — «заморозка» поточної конфігурації системи, яка дозволяє миттєво повернутися до неї, якщо під час експериментів у терміналі щось пішло не так.**

**CLI (Command Line Interface) / Інтерфейс командного рядка — спосіб взаємодії з комп'ютером за допомогою введення текстових команд (термінал), замість натискання іконок мишкою.**

**Environment Variables / Змінні оточення — іменовані об'єкти в пам'яті (наприклад, $var_name), що зберігають дані, які використовуються системою або програмами під час роботи.**

**Network Address Translation (NAT) / Трансляція мережевих адрес — тип підключення, при якому віртуальна машина отримує доступ до інтернету через IP-адресу вашого реального комп'ютера, залишаючись при цьому невидимою для зовнішньої мережі.**

---

# Хід виконання роботи:

---

## 1. Клонування та експорт віртуальної системи

     1. У середовищі VirtualBox обрав робочу ОС (Work-case 2), натиснув праву кнопку миші та обрав пункт Clone (Клонувати).

<img width="457" height="579" alt="image" src="https://github.com/user-attachments/assets/93aca39f-6610-45dd-90dc-491157788e74" />

     2. У вікні налаштувань вказав ім'я для нової машини (наприклад, Work-case-3-Clone).
     3. Обов'язково обрав пункт Generate new MAC addresses for all network adapters (Згенерувати нові MAC-адреси), щоб уникнути конфліктів у мережі.
     4. Обрав тип клонування: Full clone (Повний клон) для створення незалежної копії.

<img width="769" height="491" alt="image" src="https://github.com/user-attachments/assets/68a6d5e8-6752-439f-91a2-e737117bbbfd" />

---

## Експорт системи для перенесення:
     1. Для перенесення ОС в інше середовище скористався функцією File -> Export Appliance (Файл -> Експорт конфігурації).

<img width="444" height="294" alt="image" src="https://github.com/user-attachments/assets/44c81fa6-cb9a-4302-a039-37f9bebc8437" />

     2. Вибрав формат .OVA та шлях для збереження файлу. Цей файл містить повний образ системи, який можна імпортувати на іншому ПК.

<img width="542" height="81" alt="image" src="https://github.com/user-attachments/assets/b1201b3c-ffd7-4d56-8c16-30b157976ed9" />

---

## 2. Організація мережевих з’єднань 

У ході роботи було розглянуто основні типи мережевих адаптерів:

• **NAT (Трансляція адрес)**: Використовується за замовчуванням. Дозволяє ОС виходити в Інтернет, але машина залишається невидимою для зовнішньої мережі.

• **Bridged (Мережевий міст)**: ВМ використовує реальну мережеву карту хоста. Вона виглядає як окремий фізичний пристрій у вашій домашній мережі.

• **Host-only (Віртуальний адаптер хоста)**: Створює мережу виключно між вашим реальним комп’ютером та віртуальними машинами. Інтернету зазвичай немає.

• **Internal Network (Внутрішня мережа)**: Повністю ізольована мережа всередині VirtualBox. Зв'язок є лише між віртуальними машинами, хост-система та інтернет недоступні.

---

## 3. Налаштування мережі та взаємодія між ОС

Для виконання завдань встановив у налаштуваннях обох машин  два адаптери: **NAT та Internal Network**.

<img width="680" height="348" alt="image" src="https://github.com/user-attachments/assets/1cc0a5ed-291c-4653-98c2-cf38e40b0678" />

<img width="722" height="337" alt="image" src="https://github.com/user-attachments/assets/6cf5dd88-6296-4132-80d5-271b60f83315" />

**Виконали команди в терміналі:**

• ip a — показує мережеві інтерфейси та IP-адреси..

<img width="627" height="439" alt="image" src="https://github.com/user-attachments/assets/0b18fc54-1876-4c96-a981-f1ad77c60866" />

• sudo ip addr add 192.168.100.10/24 dev eth1 - призначення статичної IP-адреси.

• sudo ip link set eth1 up - увімкнення інтерфейсу.

<img width="422" height="86" alt="image" src="https://github.com/user-attachments/assets/6f31c0d3-8008-48ec-bb32-db1b41f40c2d" />

• ping 192.168.100.10 - перевірка зв’язку між ВМ.

<img width="547" height="233" alt="image" src="https://github.com/user-attachments/assets/2511a678-bb34-47dd-b817-ad500b3920dd" />

• ping google.com - перевірка доступу до Інтернету

<img width="627" height="197" alt="image" src="https://github.com/user-attachments/assets/0d9a5bf9-1eed-47f4-b5e8-0aeaccc8bdaf" />


• **Перевірка інтернету**:
Запустив браузер (Firefox) на обох ОС та перевірив доступ до YouTube, що підтвердило коректність роботи NAT.

<img width="957" height="913" alt="image" src="https://github.com/user-attachments/assets/a9a39f41-4f44-44c1-a6e7-fe1dad93f145" />

• Обмін повідомленнями (Chat):

Використав утиліту netcat(чат між машинами).
1. На першій ОС відкрив порт: nc -l 4444
2. На другій ОС підключився до першої: nc 192.168.100.10 4444
(Результат: текст, введений в одному терміналі, з'являється в іншому).

<img width="543" height="121" alt="image" src="https://github.com/user-attachments/assets/c9026771-43de-4467-be48-ff6b208545c8" />

<img width="361" height="125" alt="image" src="https://github.com/user-attachments/assets/cfa2e449-ccaa-4dc4-8e09-80e3ed09e8d0" />

(останнє Hello передалось з одніє ВМ на іншу)

  • Спільна папка (Network Share):
Налаштував спільну папку через меню VirtualBox Devices -> Shared Folders. Монтування в Linux виконав командою: 

<img width="1073" height="630" alt="image" src="https://github.com/user-attachments/assets/603f83b9-fe13-4361-9e32-87a53caec9e8" />

І відразу папка, яку створили з'явиться на обох машинах.

---


## 4. Обмін інформацією з основною ОС (Windows)

**Способи**
- Shared Folder (найзручніше) - налаштовується у VirtualBox, працює постійно.

- Drag & Drop - потрібно встановити Guest Additions.

- USB-накопичувач - передача USB у ВМ.

---

**Копіювання аудіо-файлу з Windows у ВМ**

1.Додати папку Windows як Shared Folder.

2. У ВМ відкрити:

**/media/sf_shared**

3.Скопіювати файл: 

**cp song.mp3 ~/Desktop**

---

**Зворотнє копіювання з ВМ у Windows**

cp document.docx /media/sf_shared

Файл автоматично з’явиться в папці Windows.

---

# Висновок

--- 

In this laboratory work, our team of two successfully mastered the fundamental skills of virtual infrastructure administration. Working collaboratively, we performed the cloning of a working OS and explored the technicalities of exporting virtual environments for cross-platform migration.
We analyzed and implemented various network configurations, establishing a stable connection between the primary virtual machine and its clone. By utilizing NAT for internet access and an Internal Network for local interaction, we demonstrated effective data exchange using terminal utilities like ping and netcat.
Furthermore, we configured seamless integration between the host system and guest machines. This experience allowed us to practice team coordination in setting up complex virtual environments, which is a crucial skill for system administration and software development
