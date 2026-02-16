# ЗВІТ
## з виконання WORK-CASE №2
**Тема:** Робота з гіпервізорами та встановлення операційних систем родини Linux

**Виконали:**
Студентки групи **БІКС-33**
* Вітер Софія Володимирівна
* Данченко Ксенія Олегівна

---

## 1. Встановлення гіпервізора
Для виконання роботи на домашню станцію було встановлено гіпервізор типу II — **Oracle VM VirtualBox**.

<img width="156" height="183" alt="image" src="https://github.com/user-attachments/assets/81222aed-29a4-4dfd-a00b-bfb1d2098263"/>

---

## 2. Базові дії у VirtualBox

### ● Створення нової віртуальної машини
Процес створення передбачає визначення імені ВМ, вибір типу операційної системи та вказання шляху до ISO-образу.

<img width="784" height="166" alt="image" src="https://github.com/user-attachments/assets/1a77d743-4471-4e42-b637-f5e810a71df8" />

Натиснути «Створити», вказати назву, тип і версію ОС, обрати обсяг RAM та створити віртуальний диск (VDI). Після цього підключити ISO-образ для встановлення операційної системи.

<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/9934c693-caff-4645-a8db-06186653f8b3" />

### ● Вибір/додавання доступного для віртуальної машини обладнання
У розділі «Налаштування» можна змінити:
1.	обсяг оперативної пам’яті та кількість процесорів;
2.	відеопам’ять;
3.	жорсткі диски та ISO-образи;
4.	USB-контролер;
5.	спільні папки та аудіо

<img width="940" height="561" alt="image" src="https://github.com/user-attachments/assets/0f5a9579-2c23-4449-8de1-386620e1b9e8" />

### ● Налаштування мережі та підключення до точок Wi-Fi
У розділі «Мережа» можна обрати тип підключення:
1.	NAT – доступ до Інтернету через хост;
2.	Міст (Bridged Adapter) – ВМ отримує IP з тієї ж мережі, що й комп’ютер. Якщо хост підключений до Wi-Fi, ВМ також матиме Інтернет.

<img width="940" height="515" alt="image" src="https://github.com/user-attachments/assets/5ebb1201-a9fc-4844-bfa9-9555e00f91bb" />

### ●	Можливість роботи із зовнішніми носіями (flash-пам’ять)
Потрібно встановити Extension Pack. Після запуску ВМ: Пристрої --> USB --> вибрати флешку, і вона з’явиться в гостьовій ОС.

<img width="940" height="462" alt="image" src="https://github.com/user-attachments/assets/ded09cda-c129-4a58-b785-509f3cc0c390" />

---

## 3.Встановили у гіпервізор Kali Linux

<img width="687" height="114" alt="image" src="https://github.com/user-attachments/assets/c660a677-1942-4756-ac7b-b40249c1bea9" />

---

##  4.Створіть другу віртуальну машину та виконайте для неї наступні дії:

### ●	Встановіть у мінімальній конфігурації з термінальним вводом-виводом без графічного інтерфейсу операційну систему GNU/Linux;

<img width="941" height="593" alt="image" src="https://github.com/user-attachments/assets/9067fd36-4e2a-4db4-ac32-1a2ba1e97da4" />

### ●	Встановіть графічну оболонку GNOME поверх встановленої в попередньому пункті ОС; 

<img width="940" height="596" alt="image" src="https://github.com/user-attachments/assets/d28813ba-1460-4c85-8d9f-2ee03d63878f" />

### ●	Встановіть додатково ще другу графічну оболонку (їх можливий перелік можна знайти в лабораторній роботі №1) та порівняйте її можливості з GNOME.

<img width="361" height="284" alt="image" src="https://github.com/user-attachments/assets/05b9bab1-3a5a-4e0f-9d5b-b4007f76c5fb" />

<img width="940" height="630" alt="image" src="https://github.com/user-attachments/assets/4811bfc2-720e-48e1-bd02-0bef37d0b165" />

---

## 5. Порівняння GNOME та XFCE
| Критерії | GNOME | XFCE |
| :--- | :--- | :--- |
| **Інтерфейс** | Сучасний, мінімалістичний | Класичний, простий |
| **Споживання ресурсів** | Високе | Низьке |
| **Швидкість роботи** | Плавна на потужних ПК | Працює швидше на ВМ |
| **Налаштування** | Обмежені (Extensions) | Гнучке налаштування |

---

## Висновок (українською мовою):

У ході виконання роботи було опановано навички роботи з гіпервізором VirtualBox, налаштування віртуальних мереж та встановлення Linux-систем. Порівняння графічних оболонок показало, що для віртуальних машин з обмеженими ресурсами раціональніше використовувати **XFCE**, тоді як **GNOME** пропонує більш сучасний користувацький досвід.

---

## Висновок (англійською мовою):

During this lab, we mastered working with the VirtualBox hypervisor, focusing on VM configuration and network setup. By installing Kali Linux and Ubuntu Server, we practiced both CLI-based management and GUI deployment. The comparison between GNOME and XFCE demonstrated that XFCE is a superior choice for virtualized environments due to its low resource overhead and high performance.
