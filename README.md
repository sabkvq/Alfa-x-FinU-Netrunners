# Alfa FinU Hack. Команда Netrunners

## Описание

<img src="https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/media/main_photo.jpg" height=200 align="right">

- Предметная область: Онлайн-банкинг
- Бизнес-задача: Создать модель, которая будет выдавать вероятность перехода в каждый из 17 продуктовых кластеров
- Целевая переменная: Продуктовый кластер, в котором клиент будет находится через год - *end_cluster*
- Результат работы модели: информация о всех клиентах, а также вероятности их переходов в каждый из кластеров через год


## Входные данные

* train_data.pqt - тренировочный датасет с данными клиентов, а также информацией о предсказанных конечных классах (скрыт по требованию Альфа-банка)
* test_data.pqt - тестовый датасет, для которого необходимо получить вероятности попадания клиента в продуктовые кластеры (скрыт по требованию Альфа-банка)
* [cluster_weights.xlsx](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/cluster_weights.xlsx) - коэффициенты значимости кластеров
* feature_description.xlsx - описание признаков датасетов
* [sample_submission.csv](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/sample_submission.csv) - файл изначального сабмишна, для отправки

## Данные полученные в ходе работы

* [best_score.zip](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/best_score.zip) - zip-файл submission с лучшим скором
* [requirements.txt](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/requirements.txt) - файл содержащий все версии библиотек для воспроизводимости
* [Визуализация данных. Команда Netrunners.ipynb](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/%D0%92%D0%B8%D0%B7%D1%83%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F%20%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85.%20%D0%9A%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0%20Netrunners.ipynb) - файл с визуализацией информации о признаках в данных
* [Ансамбль из двух разных моделей. Команда Netrunners.ipynb](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/%D0%90%D0%BD%D1%81%D0%B0%D0%BC%D0%B1%D0%BB%D1%8C%20%D0%B8%D0%B7%20%D0%B4%D0%B2%D1%83%D1%85%20%D1%80%D0%B0%D0%B7%D0%BD%D1%8B%D1%85%20%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D0%B5%D0%B9.%20%D0%9A%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0%20Netrunners.ipynb) - файл с кодом, предобработкой данных, а тажке финальным ансамблем
* [Результаты разных submissions. Команда Netrunners.pdf
](https://github.com/sabkvq/Alfa-x-FinU-Netrunners/blob/main/%D0%A0%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D1%8B%20%D1%80%D0%B0%D0%B7%D0%BD%D1%8B%D1%85%20submissions.%20%D0%9A%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%B0%20Netrunners.pdf) - файл с информацией об изменениях в коде с последующем изменением метрики roc-auc на разных submission - файлах


## Этапы работы

1. Получение всех доступных данных
2. Создание рабочего пространства в Google Colab и Drive
3. Подгрузка данных и работа с начало работы с ними
4. Статистический анализ данных
5. Визуальный анализ данных
6. Создание функций для заполнения данных в числовых признаках
7. Заполнение пропусков в числовых признаках
8. Создание функций для заполнения данных в категориальных признаках
9. Заполнение пропусков в категориальных признаках
10. Создания набора функций для генерации новых признаков
11. Проведение генерации признаков
12. Селекция признаков
13. Избавление от ненужных признаков, путем построения тепловой карты корреляций
14. Создание CatBoost-модели (SymmetricTree)
15. Тестирование модели на разных датасетах, обучение модели
16. Подбор гиперпараметров модели
17. Создание CatBoost-моделей в виде ансамбля (SymmetricTree и Depthwise)
18. Тестирование модели
19. Подбор гиперпараметров
20. Подбор коэффициентов для объединения предсказаний модели (лучший скор - 30% SymmetricTree и 70% Depthwise)
21. Создание репозитория в GitHub
22. Наполнение репозитория
23. Создание презентации
24. Защита результатов проекта


## Действия, не принесшие результата

* Создание кодировщика для кодирования категориальных данных - экспоненциальный рост признаков в данных до 15 тыс.
* Проведение кластеризацию с помощью t-SNE - не хватило ресурсов GPU в Kaggle
* Уменьшение размерности с помощью PCA (метода главных компонент) - не хватило ресурсов GPU в Google Colab
* Построение модели градиентного бустинга над стэкингом - не хватило ресурсов GPU в Google Colab
* Построение модели логистической регрессии над стэкингом - ухудшение результата метрики
* Построение временных рядов - малое количество информации
* Построение модели Denoising Transformer Autoencoder для генерации эмбеддингов - недостаток оперативной памяти, а также мощностей для запуска


## Команда Netrunners
- [Надежда Агафонова](https://t.me/LanderWine) | Капитан команды
- [Артур Артиков](https://github.com/ArturArtikov/) | Data Scientist | Data Analyst
- [Степан Золин](https://github.com/DrHeog) | ML Engineer
- [Рамиль Габдрахманов](https://github.com/ramil2911) | ML-Engineer
- [Сергей Быков](https://github.com/sabkvq) | Data Analyst

## Используемый стек и технологии

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
