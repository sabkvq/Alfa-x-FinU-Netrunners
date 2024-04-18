# Alfa FinU Hack. Команда Netrunners

## Описание

<img src="https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/media/main_photo.jpg" height=300 align="right">

- Предметная область: Онлайн-банкинг
- Бизнес-задача: Создать модель, которая будет выдавать вероятность перехода в каждый из 17 продуктовых кластеров
- Целевая переменная: Продуктовый кластер, в котором клиент будет находится через год - *end_cluster*
- Результат работы модели: Модель предсказывающая вероятности перехода в каждый из 17 продуктовых кластеров клиента через год

</br>
</br>

## Входные данные

* train_data.pqt - тренировочный датасет с данными клиентов, а также информацией о предсказанных конечных классах (скрыт по требованию Альфа-банка)
* test_data.pqt - тестовый датасет, для которого необходимо получить вероятности попадания клиента в продуктовые кластеры (скрыт по требованию Альфа-банка)
* [cluster_weights.xlsx](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/cluster_weights.xlsx) - коэффициенты значимости кластеров
* [feature_description.xlsx](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/feature_description.xlsx) - описание признаков датасетов
* []

## Этапы работы


1. Получение всех доступных данных
2. Создание рабочего пространства в Google Colab и Drive
3. Подгрузка данных и работа с ними
4. Статистический анализ данных
5. Визуальный анализ данных
6. Заполнение пропусков в категориальных признаках
7. Заполнение пропусков в числовых признаках
8. Генерация новых признаков
10. Избавление от ненужных признаков, путем построения тепловой карты корреляций
11. Создание модели на LightGBM
12. Написание функций для преобразования данных
13. Обновление исходных данных, с учетом заполнения пропусков
14. Использование CatBoost для получения результата
15. Отбор признаков для повышения качества модели
16. Блендинг
17. Наполнение репозитория в GitHub
18. Создание презентации
19. Защита результатов проекта

## Команда
- Надежда Агафонова
- [Артур Артиков](https://github.com/ArturArtikov/)
- [Степан Золин](https://github.com/DrHeog)
- [Рамиль Габдрахманов](https://github.com/ramil2911)
- [Сергей Быков](https://github.com/sabkvq)

## Используемый сте и технологии

![Google Colaboratory](https://img.shields.io/badge/Google%20Colaboratory-ffffff.svg?style=for-the-badge&logo=google-colab&logoColor=orange)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)
![Seaborn](https://img.shields.io/badge/Seaborn-%231F6F70.svg?style=for-the-badge)
![Scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![ChromaDB](https://img.shields.io/badge/ChromaDB-%231d2f3e.svg?style=for-the-badge)
![CatBoost](https://img.shields.io/badge/CatBoost-%23ffcc00.svg?style=for-the-badge)
![Microsoft PowerPoint](https://img.shields.io/badge/Microsoft_PowerPoint-B7472A?style=for-the-badge&logo=microsoft-powerpoint&logoColor=white)
![Microsoft Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
