# New York City Taxi Trip Duration

Представьте, что вы заказываете такси из одной точки Нью-Йорка в другую, причём необязательно, что конечная точка должна находиться в пределах города. Сколько вы должны будете заплатить за поездку?

Известно, что стоимость такси в США рассчитывается на основе фиксированной ставки и тарифной стоимости, величина которой зависит от времени и расстояния. Тарифы варьируются в зависимости от города.

В свою очередь, время поездки зависит от множества факторов, таких как направление поездки, время суток, погодные условия и так далее.

Таким образом, если мы разработаем алгоритм, способный определять длительность поездки, мы сможем прогнозировать её стоимость самым тривиальным образом, например, просто умножая стоимость на заданный тариф.

Задача, которую мы будем решать, была представлена в качестве [Data Science-соревнования](https://www.kaggle.com/competitions/nyc-taxi-trip-duration/overview) с призовым фондом в 30 000 $ на платформе Kaggle в 2017 году.

Будет предоставлен набор данных, содержащий информацию о поездках на жёлтом такси в Нью-Йорке за 2016 год. Первоначально данные были выпущены Комиссией по Такси и Лимузинам Нью-Йорка и включают в себя информацию о времени поездки, географических координатах, количестве пассажиров и несколько других переменных.


**Бизнес-задача:** определить характеристики и с их помощью спрогнозировать длительность поездки на такси.

**Техническая задача:** построить модель машинного обучения, которая на основе предложенных характеристик клиента будет предсказывать числовой признак — время поездки такси, то есть решить задачу регрессии.


## Основные цели:
- Сформировать набор данных на основе нескольких источников информации.
- Спроектировать новые признаки с помощью Feature Engineering и выявить наиболее значимые при построении модели.
- Исследовать предоставленные данные и выявить закономерности.
- Построить несколько моделей и выбрать из них ту, которая показывает наилучший результат по заданной метрике.
- Спроектировать процесс предсказания длительности поездки для новых данных.
- Загрузить своё решение на платформу Kaggle, тем самым поучаствовав в настоящем Data Science-соревновании.

## Основные этапы:
1. Первичная обработка данных

    * Сформировать набор данных на основе предложенных источников информации.
    * Обработать пропуски и выбросы в данных.

2. Разведывательный анализ данных (EDA)

    * Исследовать данные.
    * Нащупать первые закономерности.
    * Выдвинуть гипотезы.

3. Отбор и преобразование признаков

    * Перекодировать и преобразовать данные.
    * Подготовить данные для решения задачи регрессии (построения модели).

4. Решение задачи регрессии: линейная регрессия и деревья решений

    * Построить первые прогностические модели.
    * Оценить качество моделей.
    * Создать baseline (отправную точку) для сравнения с более сложными моделями.
    * Ответь на вопрос: «Решаема ли вообще представленная задача?»

5. Решение задачи регрессии: ансамбли моделей и построение прогноза

    * Доработать предсказание с использованием более сложных алгоритмов.
    * Оценить, с помощью какой модели возможно сделать более качественные прогнозы.
## Описание данных:
### Данные о клиенте и таксопарке:
- id — уникальный идентификатор поездки;
- vendor_id — уникальный идентификатор поставщика услуг (таксопарка), связанного с записью поездки.

### Временные характеристики:
- pickup_datetime — дата и время, когда был включён счётчик поездки;
- dropoff_datetime — дата и время, когда счётчик был отключён.

### Географическая информация:
- pickup_longitude — долгота, на которой был включён счётчик;
- pickup_latitude — широта, на которой был включён счётчик;
- dropoff_longitude — долгота, на которой счётчик был отключён;
- dropoff_latitude — широта, на которой счётчик был отключён.

### Прочие признаки:
- passenger_count — количество пассажиров в транспортном средстве (введённое водителем значение);
- store_and_fwd_flag — флаг, который указывает, сохранилась ли запись о поездке в памяти транспортного средства перед отправкой поставщику (Y — хранить и пересылать, N — не хранить и не пересылать поездку).

### Целевой признак:
- trip_duration — продолжительность поездки в секундах.


Более подробно можно изучить в файле [nyc-taxi-duration.ipynb](https://github.com/IAskarov/NYC_Taxi_ML/blob/master/nyc-taxi-duration.ipynb)
