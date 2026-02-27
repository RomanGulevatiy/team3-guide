# Team 3 - Стартовий гайд

> [!NOTE]
> Покроковий гайд для роботи в команді.
> 
> **Питання/пропозиції?** -> Discord: `Java pro > #team-3`

---

# Навігація

1. [Налаштування IntelliJ IDEA](#1-налаштування-intellij-idea)
2. [Налаштування File Header](#2-налаштування-file-header)
3. [Основи Git та GitHub](#3-основи-git-та-github)
   - [Що таке Git?](#31-що-таке-git)
   - [Підключення GitHub акаунту в IntelliJ IDEA](#32-підключення-github-акаунту-в-intellij-idea)
   - [Клонування репозиторію](#33-клонування-репозиторію)

---

## 1. Налаштування IntelliJ IDEA

Для роботи над проєктом краще використовувати версію **IntelliJ IDEA Ultimate** (не Community!).

### Як отримати Ultimate безкоштовно (для студентів)

1. Перейдіть на сайт [jetbrains.com/academy](https://www.jetbrains.com/academy/student-pack/)
2. Натисніть **"Request now"**
3. Зареєструйтесь за університетською поштою (`@duikt.edu.ua`)
4. На пошту прийде лист - підтвердіть реєстрацію
5. Завантажте та встановіть IntelliJ IDEA Ultimate за посиланням з листа

> Покрокова інструкція від університету: [посилання](https://duikt.edu.ua/uploads/n_11828_56886710.pdf)

![Intellij IDEA Ultimate](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/intellij-ultimate.png)

---

## 2. Налаштування File Header

Щоб у кожному файлі автоматично з'являвся ваш підпис - пропоную налаштувати шаблон один раз.

### Кроки:

1. Двічі натисніть `Shift` -> відкриється пошук
2. Введіть `File and Code Templates` -> оберіть його зі списку
3. Перейдіть у вкладку **`Includes`**
4. Оберіть **`File Header`**
5. Вставте текст нижче (замінивши дані на свої)

> [!TIP]
> Дані вкажіть **англійською**, спочатку ім'я, потім прізвище.\
> змінна `${DATE}` - встановлює поточний час

```java
/**
 * Created by Ім'я Прізвище on ${DATE}.
 * github github.com/ваш-username
 */
```

---

## 3. Основи Git та GitHub

### 3.1. Що таке Git?

**Git** - це система, яка зберігає всю історію змін у коді. Уявіть, що кожен ваш `commit` - це збереження в грі: ви завжди можеш повернутися до будь-якої точки.

**GitHub** - це сайт, де зберігається спільний код нашої команди (хмара для Git).

> Раджу переглянути відео для кращого розуміння -> [Git и GitHub для новичков](https://youtu.be/EeARyFrZsnU?si=0tKs882tJo4s9Qkr)

---

### 3.2. Підключення GitHub акаунту в IntelliJ IDEA

Після встановлення IntelliJ IDEA треба увійти в свій GitHub - це робиться один раз.

### Кроки:

1. Відкрийте File -> Settings (або `Ctrl + Alt + S`)
2. Перейдіть в `Version Control -> GitHub`
3. Натисніть `+` (додати акаунт) -> оберіть `Log In with Token`
4. У новому вікні натисніть сіру кнопку `Generate`
5. Відкриється браузер - оберіть усі чекбокси і згенеруйте токен
6. Вставте токен в поле `Token:   ` всередині IntelliJ -> `Add account`

![GitHub token](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/github-token.png)

---

### 3.3. Клонування репозиторію

**Клонування** - це завантаження проєкту з GitHub на ваш комп'ютер.

**Один раз на початку роботи:**

1. Перейдіть на сторінку [репозиторію](https://github.com/Java-Spring-Sprint-Class/teamwork-management-system-team-3) на GitHub
2. Натисніть зелену кнопку **`<> Code`**
3. Скопіюйте посилання (HTTPS)
4. Відкрийте IntelliJ IDEA -> `File -> New -> Project from Version Control`
5. Вставте посилання -> натисніть **Clone**

---
