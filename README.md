<div align="center">

# Team 3 - Стартовий гайд

Українська • [English](README-en.md) • [Русский](README-ru.md)

</div>

> [!NOTE]
> Цей репозиторій - памʼятка для швидкого пошуку відповіді. Якщо щось забули - знайдіть потрібний розділ і освіжіть памʼять.
>
> **Питання/пропозиції?** -> Discord: `Java pro` -> `#team-3`

---

## Навігація

1. [Підготовка середовища](#1-підготовка-середовища)
   - [IntelliJ IDEA Ultimate](#11-intellij-idea-ultimate)
   - [File Header](#12-file-header)
2. [Основи Git](#2-основи-git)
   - [Що таке Git і GitHub?](#21-що-таке-git-і-github)
   - [Підключення GitHub акаунту](#22-підключення-github-акаунту)
   - [Клонування репозиторію](#23-клонування-репозиторію)
3. [Щоденна робота](#3-щоденна-робота)
   - [Гілки (branches)](#31-гілки-branches)
   - [Commit](#32-commit)
   - [Push](#33-push)
4. [Pull Request (PR)](#4-pull-request-pr)
   - [Як відкрити PR](#41-як-відкрити-pr)
   - [Якщо отримали коментар](#42-якщо-отримали-коментар)

---

## 1. Підготовка середовища

### 1.1. IntelliJ IDEA Ultimate

Для роботи над проєктом використовуйте **IntelliJ IDEA Ultimate** (не Community).

> [!TIP]
> Студентам - безкоштовно. Покрокова інструкція від університету: [посилання](https://duikt.edu.ua/uploads/n_11828_56886710.pdf)

1. Перейдіть на [jetbrains.com/academy](https://www.jetbrains.com/academy/student-pack/) -> **"Request now"**
2. Зареєструйтесь за університетською поштою (`@duikt.edu.ua`)
3. Підтвердіть реєстрацію через лист на пошті
4. Завантажте та встановіть IntelliJ IDEA Ultimate за посиланням з листа

![Intellij IDEA Ultimate](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/intellij-ultimate.png)

---

### 1.2. File Header

File Header - автоматичний підпис автора у кожному новому файлі. Налаштовується один раз.

1. Двічі натисніть `Shift` -> введіть `File and Code Templates` -> оберіть зі списку
2. Вкладка **Includes** -> **File Header**
3. Вставте шаблон (замініть на свої дані):

> [!TIP]
> Імʼя та прізвище - англійською. `${DATE}` - встановлює поточний час.

```java
/**
 * Created by FirstName LastName on ${DATE}.
 * github: github.com/your-username
 */
```

---

## 2. Основи Git

### 2.1. Що таке Git і GitHub?

**Git** - система що зберігає повну історію змін у коді. Кожен `commit` - точка збереження, до якої можна повернутись. **GitHub** - хмарний сервіс де зберігається спільний репозиторій команди.

---

### 2.2. Підключення GitHub акаунту

Виконується один раз після встановлення IntelliJ IDEA.

1. `File -> Settings` (або `Ctrl + Alt + S`) -> `Version Control -> GitHub`
2. Натисніть `+` -> `Log In with Token`
3. Натисніть **Generate** - відкриється браузер
4. Оберіть усі чекбокси -> згенеруйте токен -> скопіюйте його
5. Вставте токен у поле **Token** -> **Add account**

---

### 2.3. Клонування репозиторію

Клонування - завантаження проєкту з GitHub на ваш компʼютер. Виконується один раз.

1. Перейдіть на [сторінку репозиторію](https://github.com/Java-Spring-Sprint-Class/teamwork-management-system-team-3) -> кнопка **`<> Code`** -> скопіюйте HTTPS посилання
2. В IntelliJ IDEA: `File -> New -> Project from Version Control`
3. Вставте посилання -> **Clone**

![GitHub clone](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/github-clone.gif)

---

## 3. Щоденна робота

### 3.1. Гілки (branches)

**Гілка** - ізольований потік змін, відокремлений від основного коду команди.

> [!CAUTION]
> Ніколи не пишіть код напряму в гілці `main`!

```
main ──●────────────────────────●── (стабільний код)
        \                      /
         ●────● feature/my-task (ваша гілка)
```

**Перед початком кожної нової задачі:**

```bash
# Переконайтесь що ви на main
git status

# Перейдіть на main (якщо до цього перебували в іншій гілці)
git checkout main

# Завантажте останні зміни
git pull

# Створіть нову гілку і перейдіть на неї
git checkout -b тип/назва-задачі
```

**Правила неймінгу гілок.** Формат: `тип/коротка-назва`. Назва - **англійською**, слова через `-`.

| Тип задачі            | Префікс     | Приклад                             |
|-----------------------|-------------|-------------------------------------|
| Нова функціональність | `feature/`  | `feature/user-login`       |
| Виправлення помилки   | `fix/`      | `fix/login-null-pointer`   |
| Рефакторинг           | `refactor/` | `refactor/user-service`    |

![Branch switching](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/branch-switching.gif)

---

### 3.2. Commit

Commit - збереження змін **локально** (на вашому пристрої).

> [!IMPORTANT]
> Назва коміту має чітко говорити **що** зроблено. Не "зміни", не "правки", не "fix2".

```bash
# Перевірте які файли змінились
git status

# Додайте файли до коміту
git add .

# Збережіть зміни
git commit -m "тип: короткий опис що зроблено"
```

**Типи комітів:**

| Тип        | Коли використовувати         | Приклад                                  |
|------------|------------------------------|------------------------------------------|
| `feat`     | Нова функціональність        | `feat: add email validation`             |
| `fix`      | Виправлення помилки          | `fix: null pointer in UserService`       |
| `refactor` | Рефакторинг без зміни логіки | `refactor: extract validation to method` |

**Правила:**
- Англійська мова
- Нижній регістр після двокрапки
- До 72 символів
- Теперішній час: `add`, `fix`, `update` (не `added`, `fixed`, `updated`)

---

### 3.3. Push

Push - відправлення локальних комітів на GitHub.

```bash
git push origin тип/назва-вашої-гілки
```

---

## 4. Pull Request (PR)

**Pull Request** - запит на злиття вашої гілки в `main`. Перед мержем код перевіряє інший член команди (reviewer).

### 4.1. Як відкрити PR

Після `git push` GitHub покаже банер **"Compare & pull request"** - натисніть його.
Або: вкладка **Pull requests** -> **New pull request**.

Заповніть форму:
- **Title:** коротко що зроблено - у форматі коміту (`feat: add user login`)
- **Description:** що зроблено, що варто перевірити, чи є нюанси
- **Reviewers:** оберіть члена команди

Натисніть **Create pull request**.

> [!WARNING]
> Не мержіть PR самостійно - тільки після approve від reviewer.

---

### 4.2. Якщо отримали коментар

1. Прочитайте коментар від reviewer
2. Внесіть зміни на тій самій гілці (локально, в IDE)
3. Збережіть зміни `git add .` -> новий `commit` і `push` - він автоматично додасться до вже відкритого PR
4. Дайте відповідь на коментар або натисніть **"Resolve conversation"**

---

[^ Повернутись до початку](#team-3---стартовий-гайд)

---

> Останнє оновлення: березень 2026 • Maintainer: [@RomanGulevatiy](https://github.com/RomanGulevatiy)
