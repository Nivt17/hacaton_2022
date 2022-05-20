# Обнаружение атак на завод по очистке воды

## Проект

### О данных
Данные подготовлены Сингапурским университетом c помощью стенда для безопасной очистки воды (Secure Water Treatment, SWaT), которая является уменьшенным вариантом реального завода. Стенд работал 11 дней, из которых 7 дней прошло в нормальном режиме (без атак и сбоев), а в оставшиеся дни проводились атаки двух типов:
 - Кибератаки через компьютерную сеть стенда.
 - Физические атаки, связанные с выводом из строя компонентов стенда (например, двигатель или насос).

Набор данных включает как состояние оборудования и характеристики очищаемой воды, так и сетевой трафик. Атаки в обучающем наборе данных размечены вручную. С помощью размеченных данных вам нужно научиться определять атаки для тестового набора данных.

### Задача
Исследовать данные. Создать модель, которая будет обнаруживать цифровые и физические атаки на оборудование промышленного предприятия.

## Решение
### Использованные библиотеки
 - pandas
 - sklearn
 - numpy
 - matplotlib
 - seaborn

### Структура проекта
#### Бизнес-анализ задач заказчика

#### Предобработка и анализ данных
Проверено:
 - Валидность типов
 - Названий столбцов 
 - Наличие пропусков 
 - Выбросов
 - Распределение целевой переменной
 - Наличие константных столбцов

![image](https://user-images.githubusercontent.com/65940534/169449561-5802a527-ce44-400d-aaff-c743bb9c2768.png)

#### Подготовка признаков
Проведено:
- Кодирование целевой переменной в номинативную шкалу.
- Разбиение выборки на тестовую и тренировочную


#### Логистическая регрессия

| Тип | Precision  | Recall | f1-score
| :---         | :---         |
| Normal   | 0.97     | 1.00 | 0.98 |
| Attack | 0.98 | 0.76 | 0.85 |

##### Confusion Matrix
![image](https://user-images.githubusercontent.com/65940534/169450950-ff99e877-d4a1-453a-830a-7f6e44a5d500.png)


##### Weight hist
![image](https://user-images.githubusercontent.com/65940534/169450740-ef437fc0-6f04-44c6-a79b-023d9686400b.png)


#### Обучение без учителя
##### K-means с оценкой главных компонент
##### Объясненная дисперсия
![image](https://user-images.githubusercontent.com/65940534/169451780-5cdc6403-a6da-4562-82ad-ffca5b5d37c4.png)

#####Распределение двух разных Главных Компонент
![image](https://user-images.githubusercontent.com/65940534/169451946-565d13e0-77d5-41c9-b7ec-7e9374fb42e9.png)

##### K-means
![image](https://user-images.githubusercontent.com/65940534/169452265-91cbb9d1-d7c2-4409-921d-83f008bc4d3c.png)

| Metric | Value |
| :---         | :---         |
| Accuracy   | 75.1     |
| F1 | 0.42 |
