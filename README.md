# Рекомендательная система книг 📚

🚧 **Проект находится на этапе разработки, но уже доступен для использования** 🚧

## Описание

Этот проект представляет собой веб-приложение, которое позволяет пользователям:

- Вводить название книги и имя и фамилию автора.
- Получать рекомендации, какую книгу стоит прочитать следующей, на основе введённых предпочтений.

Проект разрабатывается с целью создания удобной и интуитивно понятной платформы для поиска новых книг, соответствующих интересам пользователей.

## Текущий прогресс

### 1. **Парсинг и предобработка данных:**

- Процесс парсинга данных был осуществлен с помощью одного парсера, который собирает данные с сайта издательства АСТ.
- После сбора данных была проведена предобработка:
  - Заполнение пропусков (например, "Без автора" или "Без жанра").
  - Удаление дубликатов и объектов с некорректными значениями.
- В результате получилось около 29 тысяч книг в базе данных.

### 2. **Рекомендации:**
- Для создания системы рекомендаций был выбран подход **Content-Based**, основывающийся на содержимом книг.
- Алгоритм использует **косинусное сходство** для оценки сходства между книгами, а также технику **TF-IDF** для учета важности слов и **TruncatedSVD** для уменьшения размерности данных.
- Когда пользователь вводит название книги, система находит самые похожие книги, используя косинусное сходство, и предлагает рекомендации:
  1. Топ-5 самых похожих книг (один автор или схожие описания).
  2. 15 случайных книг с сходством выше 50%.

### 3. **Автоматизация:**
- Настроен **ETL процесс** для автоматической обработки данных с использованием **cron**, который выполняется раз в два месяца.

### 4. **Фронтенд и интеграция:**
- Разработан интерфейс на **Flask**, где пользователи могут вводить название книги и получать рекомендации.
- Проект подключен к **PostgreSQL** на платформе Railway для хранения данных о книгах и предпочтениях пользователей.

### 5. **Docker и деплой:**
- Весь проект упакован в **Docker-контейнер** для удобства развертывания.
- Проект успешно задеплоен на **Railway**, доступен по ссылке: [сайт проекта](https://booksrecsys-production.up.railway.app/)

## Установка

1. Клонируйте репозиторий:
   ```bash
   git clone https://github.com/Nikarashi/Books_recsys.git

Если у вас есть идеи или предложения, свяжитесь со мной через [telegram](https://t.me/Nikarashi).