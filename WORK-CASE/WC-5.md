# ЗВІТ

## з виконання WORK-CASE №5

**Виконали:**

Студентки групи **БІКС-33**
* Вітер Софія Володимирівна
* Данченко Ксенія Олегівна

## 1. Робота з периферійними пристроями в Linux

### 1.1 — Механізм роботи ОС Linux з пристроями на прикладі флешки та принтера

У Linux всі пристрої розглядаються як файли, які знаходяться в каталозі `/dev`.

#### Флешка (USB-накопичувач)

При підключенні:
- Ядро Linux визначає пристрій (наприклад `/dev/sdb1`)
- Система може автоматично змонтувати його (через `udev` + `automount`)
- Або користувач монтує вручну

#### Принтер

Для роботи з принтером використовується система друку CUPS (Common UNIX Printing System).

Її взаємодія:
- Керує чергою друку
- Взаємодіє з драйверами
- Приймає завдання друку

### 1.2 — Що таке монтування

Це процес підключення файлової системи пристрою до дерева каталогів Linux.

Використовується для доступу до файлів на пристрої та роботи з USB, дисками, ISO-образами.

#### Як працює

1. Створення точки монтування:

```Bash
sudo mkdir /mnt/usb
```

2. Монтування:

```Bash
sudo mount /dev/sdb1 /mnt/usb
```

3. Відмонтування:

```Bash
sudo umount /mnt/usb
```

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

1. Automount — mechanism that automatically mounts a storage device when it is connected to the system, without requiring manual user intervention.

2. Block Device — type of hardware device that stores data in fixed-size blocks (e.g., hard drives, USB flash drives) and is accessed via files in `/dev`.

3. CUPS (Common UNIX Printing System) — printing system used in Linux and Unix-like operating systems that manages print jobs, printers, and queues.

4. Driver — software that allows the operating system to communicate with hardware devices such as printers, USB drives, and other peripherals.

5. Mount Point — directory in the Linux file system where a storage device is attached and made accessible to the user.

6. Mounting — process of attaching a file system from a storage device to a specific directory (mount point) in the Linux file hierarchy.

7. Unmounting — process of safely detaching a mounted file system, ensuring that all data is written and no processes are using the device.

8. Print Queue — list of print jobs waiting to be processed by the printer, managed by the printing system (CUPS).

9. File System — method and data structure used by the operating system to organize and store files on a storage device (ext4, FAT32, exFAT).

10. Filesystem Hierarchy — structure of directories in Linux, starting from the root directory `/`, where all files and devices are organized.

---

## Висновок (Conclusion)

This laboratory work explored the integration and utilization of peripheral devices, specifically a USB flash drive and a printer, within the Linux operating system. A key focus was the mounting process, which bridges external storage with the file system to facilitate read and write operations. A comparative analysis between Linux and Windows revealed that Linux delivers superior flexibility and system transparency, whereas Windows prioritizes user convenience through automation. The practical exercises confirmed that hardware management in Linux can be efficiently executed via both the graphical user interface (GUI) and the command-line interface (CLI), highlighting the system's versatility and the enhanced operational control it provides to the user.
