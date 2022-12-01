# Ml-Agent в экономической системе. [in GameDev]
Отчет по лабораторной работе #5 выполнил(а):
- Демина Анастасия Викторовна
- РИ210942
- Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Цель работы
### Изучить способ интеграции экономической системы в проект Unity и обучения ML-Agent'а.

## Задание 1
### Ознакомиться с работой Ml-Agent на модели в предоставленном проекте Unity.
Ход работы:

- Скачала и открыла проект в Unity, установила пакеты, необходимые для работы MlAgent.
- Создала и активировала виртуальное пространство в Anaconda Prompt,  также установила требуемые пакеты.
- Запустила обучение Ml-Agent и увидела сообщение о считывании yaml-файла, что говорит о правильной установке:

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/1.png)

- Для повышения скорости обучения увеличила количество TargetAreaEconomic до 24х:

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/2.png)

- Построила графики для оценки результатов обучения, используя TensorBoard:

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/3.png)


## Задание 2
### Изменить параметры файла yaml и определить, какие из параметров влияют на обучение модели и каким образом.
Ход работы:



## Задание 3
### Описать результаты, выведенные в TensorBorder.
Ход работы:
- Cumulative reward - cреднее вознаграждение за эпизод для всех агентов. Могут наблюдаться небольшие взлеты и падения.
- Episode Length - cредняя продолжительность каждого эпизода в среде для всех агентов.
- Policy Loss - средняя величина функции policy loss. Соотносится с тем, насколько сильно меняется процесс принятия решений.
- Value Loss - cредняя потеря обновления функции значения. Коррелирует с тем, насколько хорошо модель способна предсказать значение каждого состояния.

## Выводы
Опробовала интеграцию экономической системы в проект Unity, с использованием ML-Agent. Изучила параметры конфигурации модели и их влияние на обучение с помощью анализа графиков TensorBoard.


| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
