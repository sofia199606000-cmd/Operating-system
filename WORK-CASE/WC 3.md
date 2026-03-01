# 🌐 Лабораторна робота: Клонування ВМ та мережева взаємодія
**👨‍💻 Виконали:** Вітер Софія та Данченко Ксенія

---

## 1. Робота у віртуальному середовищі

### Клонування віртуальної ОС (Work-case 2)
Клонування дозволяє створити ідентичну копію налаштованої системи. Нижче продемонстровано всі етапи процесу:

<p align="center">
  <img src="https://i.ibb.co/SXYzXxjV/image.png" width="32%" />
  <img src="https://i.ibb.co/0R90z8LP/image.png" width="32%" />
  <img src="https://i.ibb.co/JjJ0xk6p/image.png" width="32%" />
</p>
<p align="center">
  <img src="https://i.ibb.co/ks4jHFWY/image.png" width="48%" />
  <img src="https://i.ibb.co/RkcQPpBH/image.png" width="48%" />
</p>

### Експорт віртуальної робочої ОС
Для перенесення ОС у інше віртуальне середовище необхідно виконати експорт конфігурації:

<p align="center">
  <img src="https://i.ibb.co/JWqgXWQ3/image.png" width="24%" />
  <img src="https://i.ibb.co/prPDN8sp/image.png" width="24%" />
  <img src="https://i.ibb.co/SwrM9CWh/image.png" width="24%" />
  <img src="https://i.ibb.co/h1xzwcg7/image.png" width="24%" />
</p>

---

## 2. Типи організації мережевих з’єднань

Опис типів мереж, що підтримуються в середовищі віртуальних машин:

### 📥 1. Трансляція мережевих адрес (NAT)
**Опис:** ВМ використовує підключення хост-ОС через трансляцію IP-адрес.
* **Особливості:** Доступ до Інтернету (✔), Доступ з локальної мережі (❌).
* **Переваги:** Безпечна ізоляція, просте налаштування.

### 🌉 2. Мережевий міст (Bridged Adapter)

**Опис:** ВМ підключається безпосередньо до фізичної мережі як окремий пристрій.
* **Особливості:** Отримує IP від роутера, стає вузлом локальної мережі.
* **Переваги:** Повноцінна взаємодія (SSH, RDP, ping).

### 🏠 3. Віртуальний адаптер хоста (Host-Only Adapter)
**Опис:** Ізольована мережа між хост-ОС і ВМ.
* **Особливості:** Інтернет відсутній, взаємодія лише Хост ↔ ВМ.
* **Переваги:** Висока ізоляція для лабораторних робіт.

### 🔒 4. Внутрішня мережа (Internal Network)
**Опис:** Повністю ізольована мережа лише для взаємодії між віртуальними машинами.
* **Особливості:** Хост та Інтернет не мають доступу до мережі.
* **Переваги:** Максимальний рівень безпеки.

---

## 3. Розгортання мережі та діагностика

### Базові команди налаштування мережі в Ubuntu:
- `ip a` — Відображає всі мережеві інтерфейси та IP-адреси.
- `hostname -I` — Виводить поточні IP-адреси пристрою.
- `sudo ip link set ens33 up/down` — Увімкнення/вимкнення інтерфейсу.
- `ping [IP]` — Перевірка доступності іншого вузла (тестування зв’язку між ВМ і клоном).
- `ss -tuln` — Перегляд відкритих портів і з’єднань.

### Перевірка доступу до Інтернет (YouTube):
<p align="center">
  <img src="https://i.ibb.co/27TjMdCt/image.png" width="48%" />
  <img src="https://i.ibb.co/d4qMn5yV/image.png" width="48%" />
</p>

### Обмін повідомленнями по локальній мережі:
<p align="center">
  <img src="https://i.ibb.co/nMQghgsD/image.png" width="32%" />
  <img src="https://i.ibb.co/MxSF2t9J/image.png" width="32%" />
  <img src="https://i.ibb.co/Z1KwdzKJ/image.png" width="32%" />
</p>

---

## 4. Обмін інформацією між Хост-ОС та ВМ

### Передача файлів з Windows на віртуальну ОС та клон:
<p align="center">
  <img src="https://i.ibb.co/jkPG9bLt/image.png" width="32%" />
  <img src="https://i.ibb.co/wNWLdNhM/image.png" width="32%" />
  <img src="https://i.ibb.co/jZMZxHdz/image.png" width="32%" />
</p>
<p align="center">
  <img src="https://i.ibb.co/kgFVZyT5/image.png" width="24%" />
  <img src="https://i.ibb.co/gLzb5fCN/image.png" width="24%" />
  <img src="https://i.ibb.co/LD77wTsK/image.png" width="24%" />
  <img src="https://i.ibb.co/0Rpd1hLR/image.png" width="24%" />
</p>
<p align="center">
  <img src="https://i.ibb.co/CKgR7vJS/image.png" width="48%" />
  <img src="https://i.ibb.co/jkkCRVGh/image.png" width="48%" />
  <img src="https://i.ibb.co/SSv9mmG/image.png" width="48%" />
</p>

### Копіювання з віртуальної ОС на основну (Windows):
<p align="center">
  <img src="https://i.ibb.co/M4tpL74/image.png" width="32%" />
  <img src="https://i.ibb.co/gbXskqjy/image.png" width="32%" />
  <img src="https://i.ibb.co/60BfMXqw/image.png" width="32%" />
</p>
<p align="center">
  <img src="https://i.ibb.co/kVt059pc/image.png" width="24%" />
  <img src="https://i.ibb.co/8DPRFrG0/image.png" width="24%" />
  <img src="https://i.ibb.co/chR2qvLv/image.png" width="24%" />
  <img src="https://i.ibb.co/7J177zkw/image.png" width="24%" />
</p>
<p align="center">
  <img src="https://i.ibb.co/Kjy2ktwr/image.png" width="48%" />
  <img src="https://i.ibb.co/Zzn1F122/image.png" width="48%" />
</p>

---

## 📝 Висновок
