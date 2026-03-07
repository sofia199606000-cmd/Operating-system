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

## Відповіді на питання

1. Пакет (Package) У середовищі Linux програма зазвичай не розповсюджується як один виконуваний файл (як .exe у Windows).
Пакет — це спеціальний стиснутий архівний файл, який містить усе необхідне для роботи певного програмного забезпечення.

2. Репозиторій — це централізоване, спеціально організоване сховище пакетів програмного забезпечення, яке зазвичай розміщується на серверах в інтернеті (рідше — на локальних серверах або дисках). Його можна порівняти з величезним каталогом або складом.
Система користувача періодично завантажує з репозиторію спеціальні індексні файли, щоб знати, які програми та яких версій доступні для встановлення. Офіційні репозиторії дистрибутивів гарантують, що програмне забезпечення перевірене, сумісне із системою та не містить шкідливого коду.


4. Встановлення нових програм у графічному середовищі Linux є інтуїтивно зрозумілим процесом, який багато в чому нагадує використання Google Play на Android або App Store на смартфонах. Хоча термінал залишається надзвичайно потужним інструментом, сучасні дистрибутиви пропонують зручні графічні інтерфейси, які приховують складність роботи із системними залежностями. Загалом ці інструменти можна поділити на дві основні категорії: магазини додатків (Software Centers) та графічні менеджери пакетів.
Магазини додатків, такі як Ubuntu Software, GNOME Software, KDE Discover або Linux Mint Software Manager, орієнтовані на звичайного користувача. Вони пропонують зручний візуальний каталог програм із розбивкою на категорії, скріншотами, детальним описом та рейтингами, відображаючи при цьому переважно лише кінцеві прикладні програми. Наприклад, для встановлення медіаплеєра VLC через Ubuntu Software достатньо відкрити цей центр програм, ввести назву "VLC" у рядок пошуку, обрати потрібний додаток зі списку результатів і натиснути кнопку "Встановити". Після цього система попросить ввести пароль користувача для підтвердження прав адміністратора, і по завершенню завантаження програма автоматично з'явиться у головному меню. Крім того, сучасні магазини додатків часто інтегрують підтримку універсальних форматів пакетів, таких як Snap або Flatpak. Це дозволяє буквально в один клік встановлювати найсвіжіші версії програм, які запускаються в ізольованому середовищі та вже містять у собі всі необхідні для роботи залежності.
З іншого боку, існують більш просунуті графічні менеджери пакетів, такі як Synaptic (для дистрибутивів на базі Debian/Ubuntu) або Pamac (для систем на базі Arch Linux). Вони слугують візуальною оболонкою для консольних утиліт на зразок APT чи Pacman. На відміну від магазинів додатків, вони відображають абсолютно всі доступні пакети, включаючи системні бібліотеки, драйвери та дрібні системні утиліти. Як приклад, для встановлення середовища розробки Geany через менеджер Synaptic потрібно запустити програму, ввівши пароль адміністратора, знайти пакет "geany" через вбудований пошук, натиснути на нього правою кнопкою миші та обрати пункт "Відмітити для встановлення". Програма автоматично проаналізує пакет і запропонує відмітити також інші системні компоненти (залежності), необхідні для роботи цього середовища. Після вашої згоди залишиться лише натиснути кнопку "Застосувати" на верхній панелі для початку процесу завантаження та інсталяції.

# Висновок

Here is the conclusion for your laboratory work, written in English as a continuous text from the perspective of a two-person team:During the execution of Laboratory Work No. 5 , our two-person team successfully achieved the primary objectives and gained hands-on experience with the Linux command-line interface, specifically the Bash shell. We thoroughly explored the Linux virtual filesystem hierarchy, including the Filesystem Hierarchy Standard (FHS) , and compared its root-based structure to the drive-letter system used in Windows. Through collaborative practice, we mastered essential navigation commands, such as pwd, ls, and various implementations of the cd command to efficiently move between directories. Furthermore, we acquired practical skills in managing files and directories by executing commands for creating (mkdir, touch) , copying (cp) , moving and renaming (mv) , and safely deleting (rm, rmdir) data. We also practiced utilizing glob characters (wildcards) for pattern matching and redirecting command output into text files using the echo command. In addition to basic file management, we expanded our knowledge by exploring software packages, repositories, and package managers, learning how to search, install, and remove applications using both terminal tools and graphical software centers. Ultimately, this teamwork solidified our theoretical knowledge and provided us with a strong practical foundation for navigating and managing Linux-based operating systems.
