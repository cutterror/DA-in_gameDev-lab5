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

После каждого изменения параметра для выявления отклонения запускала обучение до Step 100 000 для анализа графиков при большем количетсве данных.

- Графики при изначальных значениях параметров:

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/base/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/base/2.png)

- Увеличила значение learning_rate до 10.0e-4. Из третьей лабораторной работы знаю, что данный параметр отвечает за начальную скорость обучения и при слишком больших значениях обучение будет нестабильно и вознаграждение не будет постоянно увеличиваться, что и видно из графиков: Learning Rate снижается значительно медленней, а значение в Cumulative reward доходит до отрицательных значений.

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/learning_rate%2010e-4/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/learning_rate%2010e-4/2.png)

- Увеличила значение beta до 10.0e-2. Данный параметр отвечает за "случайность" политики. Entropy резко растёт вверх, а Cumulative reward неизменно.

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/beta%2010e-2/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/beta%2010e-2/2.png)

- Увеличила значение epsilon до 0.8. Отвечает за то, насколько быстро политика может развиваться во время обучения. Entropy резко растёт вверх.

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/epsilon%200.8/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/epsilon%200.8/2.png)

- Уменьшила значение lambd до 0.2. Отвечает за то, насколько агент полагается на свою текущую оценку стоимости при вычислении обновленной оценки стоимости. График Cumulative reward похож на параболу, обучение не стабильно.

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/lambd%200.2/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/lambd%200.2/2.png)

- Увеличила значение num_epoch до 10. Отвечает за количество проходов через буфер опыта при выполнении оптимизации градиентного спуска. График Cumulative reward опускается практически до отрицательных значений, медленно растёт. Обучение не стабильно.

![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/num%20epoch%2010/1.png)
![Image alt](https://github.com/cutterror/DA-in_gameDev-lab5/blob/main/images/num%20epoch%2010/2.png)

## Задание 3
### Описать результаты, выведенные в TensorBorder.
Ход работы:
- Cumulative reward - cреднее вознаграждение за эпизод Должно последовательно увеличиваться с течением времени. Имеет небольшие колебания.
- Episode Length - длительность эпизода - время, за которое агент решает задачу в процессе обучения. В данной модели - константа.
- Policy Loss - соотносится с тем, насколько сильно меняется процесс принятия решений. Как правило, должно быть меньше 1,0.
- Value Loss - изменение ценности, будет увеличиваться по мере увеличения вознаграждения, а после становления стабильного награждения должно уменьшаться.
- Entropy - соответствует тому, насколько случайны решения. Должно последовательно уменьшаться с течением обучения.
- Learning Rate - скорость обучения, будет постепенно уменьшаться с течением времени.

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
