# Отчёт: доработка лекции №2

Викулова Елизавета

Работа выполнена совместно с ИИ.

Дата проверки источников: 5 ноября 2026 года.

## 1. Рейтинг и динамика

Проверены [рейтинг DB-Engines](https://db-engines.com/en/ranking) за ноябрь 2026 и [Popularity trends](https://db-engines.com/en/ranking_trend/). Добавлены компактный топ-10 и отдельный слайд с годовым сравнением. Первые четыре места сохраняют реляционные СУБД; мультимодельные возможности не отменяют базовую модель. [Методика](https://db-engines.com/en/ranking_definition) измеряет популярность по публичным сигналам, а не быстродействие и долю рынка. Вывод о сохранении роли SQL — интерпретация рейтинга.

## 2. Свежий кейс

В [итогах Yandex Cloud за 2025 год](https://yandex.cloud/ru/blog/financial-results-2025) приведён кластер ClickHouse внешнего заказчика объёмом 2,5 ПБ. Кейс относится к колоночной аналитике; публикация не раскрывает имя заказчика и сравнение скорости до/после. Число не относится ко всем клиентам или к единой базе Яндекса.

## 3. Фактчекинг и уточнения

[Официальная новость Яндекса](https://www.yandex.ru/company/news/2016-0615) подтверждает происхождение ClickHouse и открытие кода 15 июня 2016 года. Статус: **подтверждено**. Дата не подменяет начало разработки.

Исправлена ошибочная строка про узлы графа в колоночной модели. Разведены [колоночная аналитика ClickHouse](https://clickhouse.com/docs/intro) и [wide-column Cassandra](https://cassandra.apache.org/doc/latest/cassandra/developing/data-modeling/intro.html). Убраны абсолютные запреты JOIN/сложных запросов: [MongoDB поддерживает $lookup](https://www.mongodb.com/docs/manual/reference/operator/aggregation/lookup/), [DynamoDB имеет запросы и вторичные индексы](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SecondaryIndexes.html). Возможности реализации не следуют автоматически из названия модели.

## 4. Личный пример

Для личного слайда я указала расписание, плейлист, заказы, контакты и заметки. ИИ помог сформулировать задачи и сопоставить модели: поиск по датам — реляционная, вложенные метаданные и текст с тегами — документная, связи между людьми — графовая. Это обоснованный вариант проектирования, а не утверждение об устройстве используемых приложений.

## 5. Тренды

Добавлен сюжет о [лицензировании Redis 8 в 2025 году](https://redis.io/blog/agplv3/): AGPLv3 добавлена как один из вариантов. Это не смена лицензий старых версий задним числом. Комментарий: кроме модели и производительности, при выборе продукта важны версия и условия использования.

## 6. Иллюстрация и промты

Генератор: встроенный ImageGen в Codex. Созданы два независимых варианта; оба сохранены в `pic/variants/`. В слайд встроен второй.

### Первый промт

```text
Isometric 3D illustration, soft pastel palette (mint green, sky blue, sandy), many translucent database columns holding small data cubes, glossy translucent elements and glass panels with data icons, clean tech style, soft studio lighting, light background, no text, no logos. Educational slide about a column-oriented database. Vertical right-column composition. -ar 3:4
```

Первый вариант перегружен дополнительными панелями и мини-схемами. Во втором промте потребована одна таблица, три колонки и одна лупа; композиция стала проще, появились широкие поля. Иллюстрация показывает идею выборочного чтения столбца, а не точную архитектуру ClickHouse.

### Второй промт

```text
Isometric 3D illustration, soft pastel palette (mint green, sky blue, sandy), exactly one small transparent table separating into three simple vertical column stacks, one subtle glass magnifying lens inspecting only one column, glossy translucent elements, clean tech style, soft studio lighting, pure light background, no text, no letters, no logos, no extra floating dashboards or repeated mini-diagrams. Single compact central scene, generous blank margins, readable at small size in the right 35 percent of an educational slide. Portrait. -ar 3:4
```

Промт повторён в HTML-комментарии исходного Markdown. Текст и подписи добавляются средствами Marp, а не генератором изображений.

## 7. Оформление и экспорт

Сокращены перегруженные описания моделей, чтобы не перекрывать заголовки и иллюстрации.

Убраны абсолютные позиции заголовков и конфликтующие сетки исходника. Оформление приведено к общему стилю: зелёные заголовки, блоки источников, отдельные текстовые и иллюстративные области; новые слайды используют scoped-стили. Удалены внешние логотипы, требовавшие сети. HTML соответствует финальному Markdown и приложен вместе с локальными картинками; готовый экспорт включается в последний коммит.

## Коммиты

https://github.com/VikulovaLiza56/miniLab2
