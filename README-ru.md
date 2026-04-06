<div align="center">

# Team 3 - Стартовый гайд

[Українська](README.md) • [English](README-en.md) • Русский

</div>

> [!NOTE]
> Этот репозиторий - шпаргалка для быстрого поиска ответов. Если что-то забыли - найдите нужный раздел и освежите память.
>
> **Вопросы или предложения?** -> Discord: `Java pro` -> `#team-3`

---

## Навигация

1. [Подготовка среды](#1-подготовка-среды)
   - [IntelliJ IDEA Ultimate](#11-intellij-idea-ultimate)
   - [File Header](#12-file-header)
2. [Основы Git](#2-основы-git)
   - [Что такое Git и GitHub?](#21-что-такое-git-и-github)
   - [Подключение GitHub аккаунта](#22-подключение-github-аккаунта)
   - [Клонирование репозитория](#23-клонирование-репозитория)
3. [Ежедневная работа](#3-ежедневная-работа)
   - [Ветки (branches)](#31-ветки-branches)
   - [Commit](#32-commit)
   - [Push](#33-push)
4. [Pull Request (PR)](#4-pull-request-pr)
   - [Как открыть PR](#41-как-открыть-pr)
   - [Если получили комментарий](#42-если-получили-комментарий)

---

## 1. Подготовка среды

### 1.1. IntelliJ IDEA Ultimate

Для работы над проектом используйте **IntelliJ IDEA Ultimate** (не Community).

> [!TIP]
> Для студентов - бесплатно. Пошаговая инструкция от университета: [ссылка](https://duikt.edu.ua/uploads/n_11828_56886710.pdf)

1. Перейдите на [jetbrains.com/academy](https://www.jetbrains.com/academy/student-pack/) -> **"Request now"**
2. Зарегистрируйтесь с университетской почтой (`@duikt.edu.ua`)
3. Подтвердите регистрацию по ссылке из письма
4. Скачайте и установите IntelliJ IDEA Ultimate по ссылке из письма

![Intellij IDEA Ultimate](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/intellij-ultimate.png)

---

### 1.2. File Header

File Header - автоматическая подпись автора в каждом новом файле. Настраивается один раз.

1. Дважды нажмите `Shift` -> введите `File and Code Templates` -> выберите из списка
2. Вкладка **Includes** -> **File Header**
3. Вставьте шаблон (замените на свои данные):

> [!TIP]
> Имя и фамилия - на английском. `${DATE}` - автоматически подставляет текущую дату.

```java
/**
 * Created by FirstName LastName on ${DATE}.
 * github: github.com/your-username
 */
```

---

## 2. Основы Git

### 2.1. Что такое Git и GitHub?

**Git** - система, которая хранит полную историю изменений в коде. Каждый `commit` - точка сохранения, к которой можно вернуться. **GitHub** - облачный сервис, где хранится общий репозиторий команды.

---

### 2.2. Подключение GitHub аккаунта

Выполняется один раз после установки IntelliJ IDEA.

1. `File -> Settings` (или `Ctrl + Alt + S`) -> `Version Control -> GitHub`
2. Нажмите `+` -> `Log In with Token`
3. Нажмите **Generate** - откроется браузер
4. Отметьте все чекбоксы -> сгенерируйте токен -> скопируйте его
5. Вставьте токен в поле **Token** -> **Add account**

---

### 2.3. Клонирование репозитория

Клонирование - это загрузка проекта с GitHub на ваш компьютер. Выполняется один раз.

1. Перейдите на [страницу репозитория](https://github.com/Java-Spring-Sprint-Class/teamwork-management-system-team-3) -> кнопка **`<> Code`** -> скопируйте HTTPS ссылку
2. В IntelliJ IDEA: `File -> New -> Project from Version Control`
3. Вставьте ссылку -> **Clone**

![GitHub clone](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/github-clone.gif)

---

## 3. Ежедневная работа

### 3.1. Ветки (branches)

**Ветка** - изолированный поток изменений, отделённый от основного кода команды.

> [!CAUTION]
> Никогда не пишите код напрямую в ветке `main`!

```
main ──●────────────────────────●── (стабильный код)
        \                      /
         ●────● feature/my-task (ваша ветка)
```

**Перед началом каждой новой задачи:**

```bash
# Убедитесь, что вы на main
git status

# Переключитесь на main (если были в другой ветке)
git checkout main

# Загрузите последние изменения
git pull

# Создайте новую ветку и переключитесь на неё
git checkout -b тип/название-задачи
```

**Правила именования веток.** Формат: `тип/короткое-название`. Название - **на английском**, слова через `-`.

| Тип задачи            | Префикс     | Пример                              |
|-----------------------|-------------|-------------------------------------|
| Новая функциональность | `feature/`  | `feature/user-login`       |
| Исправление ошибки    | `fix/`      | `fix/login-null-pointer`   |
| Рефакторинг           | `refactor/` | `refactor/user-service`    |

![Branch switching](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/branch-switching.gif)

---

### 3.2. Commit

Commit - сохранение изменений **локально** (на вашем устройстве).

> [!IMPORTANT]
> Название коммита должно чётко говорить **что** сделано. Не "изменения", не "правки", не "fix2".

```bash
# Проверьте, какие файлы изменились
git status

# Добавьте файлы к коммиту
git add .

# Сохраните изменения
git commit -m "тип: краткое описание что сделано"
```

**Типы коммитов:**

| Тип        | Когда использовать           | Пример                                   |
|------------|------------------------------|------------------------------------------|
| `feat`     | Новая функциональность       | `feat: add email validation`             |
| `fix`      | Исправление ошибки           | `fix: null pointer in UserService`       |
| `refactor` | Рефакторинг без смены логики | `refactor: extract validation to method` |

**Правила:**
- Английский язык
- Строчные буквы после двоеточия
- До 72 символов
- Настоящее время: `add`, `fix`, `update` (не `added`, `fixed`, `updated`)

---

### 3.3. Push

Push - отправка локальных коммитов на GitHub.

```bash
git push origin тип/название-вашей-ветки
```

---

## 4. Pull Request (PR)

**Pull Request** - запрос на слияние вашей ветки в `main`. Перед мержем код проверяет другой член команды (reviewer).

### 4.1. Как открыть PR

После `git push` GitHub покажет баннер **"Compare & pull request"** - нажмите его.
Или: вкладка **Pull requests** -> **New pull request**.

Заполните форму:
- **Title:** коротко что сделано - в формате коммита (`feat: add user login`)
- **Description:** что сделано, что стоит проверить, есть ли нюансы
- **Reviewers:** выберите члена команды

Нажмите **Create pull request**.

> [!WARNING]
> Не мержите PR самостоятельно - только после approve от reviewer.

---

### 4.2. Если получили комментарий

1. Прочитайте комментарий от reviewer
2. Внесите изменения на той же ветке (локально, в IDE)
3. Сохраните изменения: `git add .` -> новый `commit` и `push` - он автоматически добавится к уже открытому PR
4. Ответьте на комментарий или нажмите **"Resolve conversation"**

---

[^ Вернуться к началу](#team-3---стартовый-гайд)

---

> Последнее обновление: апрель 2026 • Maintainer: [@RomanGulevatiy](https://github.com/RomanGulevatiy)
