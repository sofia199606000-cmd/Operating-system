# ЗВІТ

## з виконання WORK-CASE №4

**Тема:** "Знайомство з командами навігації по файловій системі та керування файлами та каталогами"

**Виконали:**

Студентки групи **БІКС-33**
* Вітер Софія Володимирівна
* Данченко Ксенія Олегівна

---

## Словник англійських термінів

**Package** — пакет; архівний файл, що містить саму програму, її конфігураційні файли та метадані, необхідні для встановлення.

**Package Manager** — менеджер пакетів; спеціальна утиліта (наприклад, APT, DNF, Pacman), що автоматизує процеси пошуку, встановлення, оновлення та видалення програмного забезпечення.

**Repository (Repo)** — репозиторій (сховище); сервер в інтернеті або локальна директорія, де зберігається колекція пакетів програмного забезпечення, доступних для завантаження.

**Dependencies** — залежності; інші пакети або системні бібліотеки, які обов'язково повинні бути встановлені для того, щоб обрана програма працювала коректно.

**Linux Distribution (Distro)** — дистрибутив Linux; конкретна версія операційної системи на базі ядра Linux (наприклад, Ubuntu, Fedora, Arch).

**Graphical User Interface (GUI)** — графічний інтерфейс користувача; візуальне середовище робочого столу.

**App Store / Software Center** — магазин додатків або центр програмного забезпечення; програма з графічним інтерфейсом для зручного пошуку та встановлення додатків.

---

## Відповіді на питання

1.1 **Пакет** — це спеціальний стиснутий архівний файл, який містить усе необхідне для роботи певного програмного забезпечення.
До його складу зазвичай входять: виконувані файли програми; бібліотеки; файли конфігурації; документація; інформація про залежності.

*Пакети створюються у певному форматі, який залежить від дистрибутива Linux.*

Наприклад:

- .deb — використовується у Debian, Ubuntu, Kali Linux

- .rpm — використовується у Fedora, Red Hat, CentOS

1.1 **Репозиторій** — це централізоване, спеціально організоване сховище пакетів програмного забезпечення, яке зазвичай розміщується на серверах в інтернеті (рідше — на локальних серверах або дисках). Його можна порівняти з величезним каталогом або складом.
Система користувача періодично завантажує з репозиторію спеціальні індексні файли, щоб знати, які програми та яких версій доступні для встановлення. Офіційні репозиторії дистрибутивів гарантують, що програмне забезпечення перевірене, сумісне із системою та не містить шкідливого коду.

*У Kali Linux список репозиторіїв зберігається у файлі:*

cat /etc/apt/sources.list

<img width="715" height="160" alt="image" src="https://github.com/user-attachments/assets/12a01eff-49e9-4813-8c2e-090d2fc928cb" />

**deb** — тип пакета (бінарні пакети)

**http://http.kali.org/kali**
 — сервер репозиторію

**kali-rolling** — гілка Kali (яка постійно оновлюється)

**main** — основні пакети

**contrib** — пакети з додатковими залежностями

**non-free** — пропрієтарне ПЗ

**non-free-firmware** — драйвери та firmware

Це офіційний репозиторій Kali Linux, через який встановлюються програми.

1.2 **Менеджер пакетів** — це спеціальна програма, яка дозволяє встановлювати, видаляти, оновлювати та керувати пакетами програм.

- **APT (Advanced Package Tool)** - надійний і широко використовуваний у дистрибутивах на основі Debian (наприклад, Ubuntu). Перевагами є простота використання і великий репозиторій програмного забезпечення. Недоліком є нижча продуктивність порівняно з деякими альтернативами.

- **DNF (Dandified YUM)** - менеджер пакетів у Fedora за замовчуванням. Він пропонує ефективне вирішення залежностей і підтримку модульних пакетів. Однак новим користувачам він може здатися складним.

- **Pacman** - легкий і швидкий, розроблений для Arch Linux. Його простота сподобається досвідченим користувачам, але йому бракує зручних для початківців функцій менеджерів з графічним інтерфейсом.

- **Zypper** - менеджер пакетів OpenSUSE. Поєднує розширені можливості з простотою використання, але менш популярний за межами OpenSUSE.

- **Portage** - менеджер пакетів Gentoo на основі вихідних кодів. Дуже добре налаштовується, ідеально підходить для досвідчених користувачів, але вимагає значного часу і досвіду.

- **Snap та Flatpak** - крос-платформні менеджери, які спрощують розповсюдження програмного забезпечення. Хоча вони працюють з різними дистрибутивами, їх недоліком може бути велика потреба у дисковому просторі.

---

2. **Менеджер пакетів у Kali Linux**

У Kali Linux використовується менеджер пакетів APT. Він працює з пакетами формату **.deb**.

**Основні команди APT**

- **Оновлення кешу пакетів** - щоб переконатися, що база даних пакетів є актуальною, скористайтеся командою:

*sudo apt update*

Це оновить список доступних пакетів та їх версій.

- **Встановлення програмного забезпечення** - APT спрощує встановлення програмного забезпечення:

*sudo apt install package-name*

Замінивши package-name на потрібний пакет.

- **Оновлення встановлених пакетів** - запустіть цю команду, щоб оновити всі встановлені пакети:

*sudo apt upgrade*

- **Пошук пакету** - пошук пакетів за назвою або описом:

*apt search package-name*

- **Видалення пакета** - видалення пакету зі збереженням його конфігураційних файлів:

*sudo apt remove package-name*

- **Для повного видалення, включаючи конфігурацію:**

*sudo apt purge package-name*

---

3. **Встановлення програм через менеджер пакетів**

- **Встановлення відеоплеєра VLC Media Player** (VLC — це універсальний медіаплеєр для відтворення відео та аудіо.)

*sudo apt install vlc*

<img width="824" height="509" alt="image" src="https://github.com/user-attachments/assets/4d9c54b0-2356-4959-b43b-bdbcb57e5125" />

Щоб перевірити чи він встановився потрібно просто ввести *vlc*

<img width="870" height="641" alt="image" src="https://github.com/user-attachments/assets/6d5447eb-6e4a-46a4-b4f6-d60d747ec351" />

- **Встановлення середовища для програмування** - вибрали середовище для Python

*sudo apt install python3*

<img width="510" height="107" alt="image" src="https://github.com/user-attachments/assets/7c3854dc-c8b9-420d-bd15-0cae8ddad21b" />

Він відразу встановлений тому будемо встановлювати С++

1. sudo apt update - оновлення списку пакетів

<img width="732" height="203" alt="image" src="https://github.com/user-attachments/assets/be894b64-96fc-4582-bc56-8d1a02a74ab2" />

2. sudo apt install g++ - встановлення компілятора C++

<img width="671" height="152" alt="image" src="https://github.com/user-attachments/assets/430bffdb-2292-4293-bc53-380404aab665" />

3. sudo apt install build-essential - встановлення повного набору для розробки

<img width="523" height="93" alt="image" src="https://github.com/user-attachments/assets/e855a667-2bec-41c1-803a-e7de0446aee4" />

5. g++ --version - перевірка встановлення

<img width="618" height="104" alt="image" src="https://github.com/user-attachments/assets/4e572a24-f8c4-49cd-beed-fefae8ea65c1" />

**Створення першої програми на С++**

<img width="235" height="168" alt="image" src="https://github.com/user-attachments/assets/d63ca90b-821c-47bb-8636-6aef85e3a73b" />

*nano hello.cpp* - створення файлу

<img width="814" height="511" alt="image" src="https://github.com/user-attachments/assets/69218ea5-0d9c-4c8e-95db-ef16f6300352" />

сама програма

Зберегти:

- Ctrl + O

- Enter

- Ctrl + X

*g++ hello.cpp -o hello* - компілятор програми 

*./hello* - запуск програми 

---

4.**Встановлення програм через графічний інтерфейс**

У графічному середовищі Kali Linux можна використовувати GNOME Software(типу як PlayMarket/ App Store)

- *sudo apt update*

- *sudo apt install gnome-software*
  
<img width="708" height="411" alt="image" src="https://github.com/user-attachments/assets/49185f15-b7df-4a18-854c-371c6a810033" />

Для відкриття програми

*gnome-software*

<img width="1027" height="582" alt="image" src="https://github.com/user-attachments/assets/72813a7f-9c6e-4c69-a8ee-4ffd999a6b62" />

---

# Висновок

Here is the conclusion for your laboratory work, written in English as a continuous text from the perspective of a two-person team:During the execution of Laboratory Work No. 5 , our two-person team successfully achieved the primary objectives and gained hands-on experience with the Linux command-line interface, specifically the Bash shell. We thoroughly explored the Linux virtual filesystem hierarchy, including the Filesystem Hierarchy Standard (FHS) , and compared its root-based structure to the drive-letter system used in Windows. Through collaborative practice, we mastered essential navigation commands, such as pwd, ls, and various implementations of the cd command to efficiently move between directories. Furthermore, we acquired practical skills in managing files and directories by executing commands for creating (mkdir, touch) , copying (cp) , moving and renaming (mv) , and safely deleting (rm, rmdir) data. We also practiced utilizing glob characters (wildcards) for pattern matching and redirecting command output into text files using the echo command. In addition to basic file management, we expanded our knowledge by exploring software packages, repositories, and package managers, learning how to search, install, and remove applications using both terminal tools and graphical software centers. Ultimately, this teamwork solidified our theoretical knowledge and provided us with a strong practical foundation for navigating and managing Linux-based operating systems.
