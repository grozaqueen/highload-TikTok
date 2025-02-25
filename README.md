# TikTok
## 1. Тема и целевая аудитория
TikTok - сервис коротких видео
### MVP
* Регистрация и авторизация
* Публикация видео
* Просмотр видео в ленте
* Взаимодействие между пользователями посредством подписок
* Фидбек к видео через лайки, реакции, комментарии
* Рекомендации
* Поиск
### Целевая аудитория
По состоянию на 2024 год:

- **Ежемесячная аудитория (MAU):** 1,69 миллиарда пользователей.
- **DAU:** 600 млн.
- **Среднее время, проводимое пользователями в приложении:** 58 минут в день. 

**Аудитория:**

- **Возрастное распределение:**
  69,4% аудитории TikTok составляют пользователи в возрасте от 18 до 34 лет.

- **Гендерное распределение:** 50,8% пользователей — мужчины, 49,2% — женщины.

- **Географическое распределение:**
По состоянию на 2024 год, TikTok имеет следующую аудиторию по странам:

| №  | Страна             | Количество пользователей |
|:---|:-------------------|:-------------------------|
| 1  | Индонезия          | 157 млн                  |
| 2  | США                | 120 млн                  |
| 3  | Бразилия           | 105 млн                  |
| 4  | Мексика            | 77 млн                   |
| 5  | Россия             | 56 млн                   |
### Ключевые решения
* Бесконечная лента видео
* Реакции на видео
* Добавление видео в закладки
* Односторонние/двусторонние подписки

## 2. Расчет нагрузки

- **Ежемесячная аудитория (MAU):** 1,69 миллиарда пользователей.
- **DAU:** 600 млн.
- **Среднее время, проводимое пользователями в приложении:** 58 минут в день.
- **Средняя длина видео - 15 секунд, средний размер - 5 МБ**
- **34 млн видео ежедневно публикуются пользователями**
- **С ноября 2021 по январь 2022 года в TikTok зарегистрировалось более 58 млн пользователей**
- **За первую половину 2024 года TikTok скачали 488,23 млн раз**
- **В среднем на 10 просмотров видео приходится 1 лайк**

### 1. Продуктовые метрики

| Метрика | Значение |
|---------|----------|
| Месячная аудитория (MAU) | 1,69 млрд пользователей |
| Дневная аудитория (DAU) | 600 млн пользователей |
| Средний размер хранилища пользователя (видео) | 34 млн видео / 600 млн DAU = 0,057 видео на пользователя в день, 1,71 видео в месяц или около 143 видео за 7 лет|
| Средний размер хранилища пользователя (ГБ) | 0,057 видео * 5 МБ = 0,285 МБ в день на пользователя, 8,55 МБ в месяц * 12 * 7 лет = 718,2 МБ = 7,182 ГБ |

#### Среднее количество действий пользователя в день 
| Действие | Значение |
|---------|----------|
| Просмотры видео | 58 минут в среднем в сутки * 60 / 15 секунд средняя длина видео = 232 просмотра в сутки |
| Публикация видео | 34 млн видео / 600 млн DAU = 0,057 видео на пользователя в день |
| Поиск | 1% от просмотров = 2 в сутки |
| Лайки | 10% от просмотров = 23 в сутки |
| Комментарии | оценим как 1% от просмотров = 2 в сутки |
| Подписки | оценим как 0,1% от просмотров = 0,2 в сутки |
| Авторизация | 58 млн/3 месяца/30 дней = 650 тысяч в сутки |

### 2. Технические метрики

#### Размер хранения данных

| Тип данных | Средний размер единицы данных | Количество данных | Размер данных |
|------------|-----------------|----------------|----------------|
| Опубликованные видео | 5 МБ 15 сек. видео | 34 млн в день | 4,7 ПБ в месяц |
| Комментарии | около 2 КБ на 1 комментарий | 2 * 30 * 1,69 млрд в месяц | 89 ТБ в месяц |

Пусть комментарий занимает около 2 кб, мы знаем, что около 2 комментариев оставляет пользователь в сутки => около 60 в месяц, а активных пользователей в месяц 1,69 млрд.

### Сетевой трафик

| Тип трафика | Пиковое потребление (Тбит/с) | Суточный объем |
|------------|-----------------|----------------|
| Просмотр видео | 95,03 | 5 МБ - средний размер видео, 232 просмотра за одним пользователем в день, 600 млн - DAU => 600 * 232 = 139,2 млрд просмотров в день => 696 ПБ/день |
| Публикация видео | 0,0369 | 5 МБ - средний размер видео, 34 млн в день публикуют = 162 ТБ/день |
| Лайки, комментарии | 0,00425 | 13,9 млрд в день * 1 КБ + 1,39 млрд в день * 2 КБ = 16.68 ТБ/день |
| Регистрация | 0,00148 | 650 тысяч в день * пусть 10 КБ на вход = 6,5 ТБ/день |
| Поиск | 0.000387 | 1,39 млрд в день * 2 КБ = 2.78 ТБ/день |

### RPS (Запросы в секунду)

| Тип запроса | RPS | пиковое RPS | 
|------------|------------|------------|
| Просмотр видео | 232 * 600 млн DAU /24/60/60 = 1611111 | 2416666 |
| Публикация видео | 0,057 видео в день публикует пользователь * 600 млн DAU /24/60/60 = 396 | 594 |
| Лайки | 13,9 млрд /24/60/60 = 161111 | 241666 |
| Комментарии | 1,39 млрд /24/60/60 = 16111 | 24166 |
| Поиск | 1,39 млрд /24/60/60 = 16111 | 24166 |
| Регистрация | 650 тысяч /24/60/60 = 8 | 12 |

## Источники
1. https://www.demandsage.com/tiktok-user-statistics
2. https://fliki.ai/blog/tiktok-video-size
3. https://techjury.net/blog/how-many-videos-are-uploaded-to-tiktok-daily/
4. https://ecommerce-platforms.com/ru/articles/tiktok-statistics
5. https://inclient.ru/tiktok-stats
6. https://domainator.by/schitaet-li-tiktok-vashi-sobstvennye-prosmotry
