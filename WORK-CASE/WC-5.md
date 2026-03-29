# ЗВІТ

## з виконання WORK-CASE №5

**Виконали:**

Студентки групи **БІКС-33**
* Вітер Софія Володимирівна
* Данченко Ксенія Олегівна

## 1. # Управління периферійними пристроями в Linux

Один із базових принципів ОС Linux полягає в тому, що будь-яке апаратне забезпечення сприймається системою як файл. Ці спеціальні файли пристроїв зберігаються у системному каталозі `/dev`.

## Робота з USB-накопичувачами (флешками)

Під час фізичного підключення зовнішнього носія відбувається наступний алгоритм дій:
- Ядро операційної системи ідентифікує новий блоковий пристрій та присвоює йому відповідне ім'я (наприклад, `/dev/sdb1`).
- Завдяки роботі підсистем `udev` та служб автомонтування (`automount`), накопичувач може бути змонтований автоматично.
- У разі відсутності графічного середовища або за потреби розширеного контролю, користувач може виконати монтування власноруч.

## Робота з принтерами

Управління процесом друку в UNIX-подібних системах стандартно здійснюється через службу **CUPS** (Common UNIX Printing System). 

До її головних завдань належить:
- Адміністрування та контроль черг друку.
- Забезпечення коректної взаємодії з драйверами друкарського обладнання.
- Прийом, обробка та маршрутизація завдань на друк від програмного забезпечення.

---

## 1.2 Сутність процесу монтування

**Монтування** — це процедура логічного інтегрування файлової системи апаратного пристрою до єдиної ієрархії каталогів (дерева каталогів) Linux. 

Цей механізм є обов'язковою умовою для отримання доступу до читання та запису даних на будь-яких носіях: жорстких дисках, USB-флешках чи підключених ISO-образах.

### Алгоритм виконання на практиці

**1. Створення точки монтування** Спочатку необхідно створити порожню директорію, яка слугуватиме "точкою входу" до файлової системи пристрою:

```bash
sudo mkdir /mnt/usb


### 1.3 — Різниця Linux та Windows

| Характеристика | Linux | Windows |
| :--- | :--- | :--- |
| Робота з пристроями | Через файли (`/dev`) | Через букви дисків (`C:`, `D:`) |
| Монтування | Явне або авто | Автоматичне |
| Гнучкість | Дуже висока | Менша |
| Драйвери | Часто вбудовані | Часто потрібно встановлювати |
| Контроль | Повний контроль через термінал | Переважно через GUI |

Linux дає більше контролю, але вимагає більше знань.

---

## 2. Практична частина

### 2.1 — Підключення флешки до VirtualBox


Флешка з'явилася безпосредньо в файловому менеджері та відображається в дереві блокових пристроїв через `lsblk`.

### 2.2 — Копіювання файлу (GUI)

Відкривши файловий менеджер, обираємо флешку та копіюємо в бажане місце.

### 2.3 — Копіювання через термінал


```Bash
cp /mnt/file.txt ~/
```


### 2.4 — Підключення принтера через CUPS

#### Встановлення та запуск CUPS 

```Bash
sudo apt install cups
```

```Bash
sudo systemctl start cups
```

### 2.5 — Друк через GUI після налаштування CUPS

### 2.6 — Друк через термінал

```Bash
lp filename
```

#### Або:

```Bash
lpr filename
```

---

## Словник (Vocabulary)

1. Automount — A system feature that seamlessly connects storage drives to the file system the moment they are plugged in, bypassing the need for manual configuration.

2. Block Device — Hardware components (like HDDs, SSDs, or USBs) that read and write data in fixed-size chunks, typically represented by device files within the /dev directory.

3. CUPS (Common UNIX Printing System) — The standard print management service for Linux and Unix-based environments, responsible for handling printers, active print jobs, and spooling.

4. Driver — A specialized software component that acts as a translator, enabling the operating system to interact effectively with external hardware like peripherals and storage drives.

5. Mount Point — A designated folder within the operating system's directory tree where the contents of an external drive become visible and accessible.

6. Mounting — The administrative procedure of linking an external storage device's file system into the main Linux directory structure so its contents can be accessed.

7. Unmounting — The secure process of disconnecting a storage device's file system from the directory tree, guaranteeing that all pending data transfers are complete before physical removal.

8. Print Queue — A structured lineup of documents scheduled for printing, overseen and executed in sequential order by the print server.

9. File System — The underlying logical architecture (such as ext4, FAT32, or exFAT) that an operating system uses to track, manage, and store data on a physical drive.

10. Filesystem Hierarchy — The standardized, tree-like organization of all Linux directories and files, branching out downward from the top-level root (/) directory.

---

## Висновок (Conclusion)

This laboratory work explored the integration and utilization of peripheral devices, specifically a USB flash drive and a printer, within the Linux operating system. A key focus was the mounting process, which bridges external storage with the file system to facilitate read and write operations. A comparative analysis between Linux and Windows revealed that Linux delivers superior flexibility and system transparency, whereas Windows prioritizes user convenience through automation. The practical exercises confirmed that hardware management in Linux can be efficiently executed via both the graphical user interface (GUI) and the command-line interface (CLI), highlighting the system's versatility and the enhanced operational control it provides to the user.
