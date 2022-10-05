# Лабораторная работа № 2 Интеграция сервиса для получения данных профиля пользователя.
Отчет по лабораторной работе #2 выполнила:
- Стрельчук Анастасия Александровна
- 1948616

Отметка о выполнении заданий:

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | * | 20 |


Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
По теме видео практических работ 1-5 повторить реализацию игры на Unity.
Привести описание выполненных действий.
- Задание 2.
В проект, выполненный в предыдущем задании, добавить систему проверки
того, что SDK подключен (доступен в режиме онлайн и отвечает на запросы);
- Задание 3.
 1) Произвести сравнительный анализ игровых сервисов Яндекс Игрыи VK Game;
 2) Дать сравнительную характеристику сервисов,описать функционал;
 3) Описать их методы интеграции с Unity;
 4) Произвести сравнение, сделать выводы;
 5) Подготовить реферат по результатам выполнения пунктов 1-4.
- Выводы.

## Цель работы
создать интерактивное приложение и изучить принципы интеграции в него игровых сервисов.

## Задание 1
### По теме видео практических работ 1-5 повторить реализацию игры на Unity. Привести описание выполненных действий.
Ход работы:
1) Создаю новый проект, по аналогии с предыдущим занятием
2) Для добавления готового персонажа логинимся на сайте Unity Asset Store
3) Через поисковую строку находим необходимый Asset, а именно: Dragon for Boss Monster. [Добавление Ассета](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%94%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%90%D1%81%D1%81%D0%B5%D1%82%D0%B0.jpg)
4) После этого, нам необходимо подключить этот внешний пакет к нашему проекту. (Window--> Package Manager) 
5) В открывшемся окне выбираем "My Assets" во вкладке "Package: in projects". После этого туда подгрузятся Ассеты, которые добавлены через личный кабинет Unity Asset Store, а именно - Dragon for Boss Monster. [Импорт пакетов](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%98%D0%BC%D0%BF%D0%BE%D1%80%D1%82%20%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BE%D0%B2.jpg)
6) Нажимаем на этот пакет и скачиваем его, далее импортируем, соглашаясь со всеми предложенными по умолчанию пакетами.
7) Нахожу и добавляю на свою сцену обьект "Green Monster", который у меня переименовываю в "Enemy", корректируя его расположение.
8) Для добавления анимации нашему дракону(Enemy), создаем в окне ассетц Animation controller(Create--->Animation controller),переименовываем.
9) Открыв его, строим связку анимации для дракона, закинув туда найденный в скачанном ранее пакете "FlyIdle", перенеся его копию в папку сцены(Ctrl+D), а оттуда перетянув на экран с зависимостями. 
10) По умолчанию у дракона стоит подгруженный пакет анимаций, поэтому нажимаем на Enemy, и в окне инспектора меняем папки, найдя необходимую в строке "Controller". [Настройка полета дракона](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%94%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%BF%D0%BE%D0%BB%D0%B5%D1%82%D0%B0.jpg)
11) Сохраняем изменения и запускаем проект - наблюдаем полет дракона. [Промежуточный итог](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%9F%D0%B5%D1%80%D1%81%D0%BE%D0%BD%D0%B0%D0%B6%20%D1%81%20%D1%8F%D0%B9%D1%86%D0%BE%D0%BC.jpg)
12) По аналогии с первой лабораторной работой - создаем 2 обьекта Энергетический щит и Яйцо дракона(GameObject--->3D--->Shere), создаем и поключаем им материал, выбрав цвет. Меняем положение в пространстве и размер. Подключаем для них компонент Rigid Body.
13) Для яйца ставим гравитацию, чтобы оно падало при запуске.
14) Для Щита ставим кинематику без гравитации, чтобы оно парило. 
15) Так как пока что яйцо нам не нужно на сцене - перетаскиваем его из окна иерархии в папку сцены окна ассетц, удаляя из окна иерархии.
16) Так как Щит нужно оставить, перетаскиваем его туда же, куда и файл Яйца, при этом оставляя на сцене. Таким обраом мы создали основные игровые обьекты, сохраняем проект. 
17) Далее произведем настройку камеры, так как это также играет важную роль в игре. Для этого выберем в окне иерархии "Main Camera". [Настройка камеры](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0%20%D0%BA%D0%B0%D0%BC%D0%B5%D1%80%D1%8B.jpg)
18) Устанавливаем указанные значения Position,Rotation, Scale, а также Projection: Orthographic, size-12, far-50. [Получаем результат](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%A0%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%20%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8%20%D0%BA%D0%B0%D0%BC%D0%B5%D1%80%D1%8B.jpg)
19) Установим настройки соотношения экрана - выберем 16 к 9 во вкладке Game. [Наблюдаем результат]
20) Далее создаем скрипт, который будет управлять перемещением персонажа: в папке сцены окна ассетц(Create--->C# Script) [Окно инспектора](https://github.com/umi0193/DA-in-GameDev-lab2/blob/main/%D0%9E%D0%BA%D0%BD%D0%BE%20%D0%B8%D0%BD%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0.jpg)
21) В скрипте создадим переменные, которые будут отвечать за скорость, уровень случайности, расстояние от краев экрана, после которых движение дракона будет меняться. 
22) Далее создаем код, который будет хранить и менять позицию дракона в равные промежутки времени. 
23) Далее, пишем код, который будет позволять менять направление движения дракона при достижении края на противоположное. 
24) Отдельно прописываем изменение скорости на противоположную при смене позиции.

Итоговый скрипт Enemy Dragon.cs: 
```cs
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
// using Time.deltaTime;

public class EnemyDragon : MonoBehaviour
{
    public GameObject dragonEggPrefab;
    public float speed = 1;
    public float timeBetweenEggDrops = 1f;
    public float leftRightDistance = 10f;
    public float chanceDirection = 0.1f; 

    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        Vector3 pos = transform.position;
        pos.x += speed * Time.deltaTime;
        transform.position = pos;

        if (pos.x < -leftRightDistance){
            speed = Mathf.Abs(speed);
        }
        else if (pos.x > leftRightDistance){
            speed = -Mathf.Abs(speed);
        }

    }

    private void FixedUpdate() {
        if (Random.value < chanceDirection){
            speed *= -1;
        }
    }
}
```

25) Далее мы приступаем к реализации сбрасывания драконом яйца. Для этого мы выбираем обьект Дракон и находим у него строку добавления префаба.ю добавляем туда префаб Яйцо дракона
26) Далее добавим в скрипт метод drop, который позволит при заданном нами интервале сбрасывать яйца [Результат]()
27) 


[]()[]()[]()[]()[]()
## Задание 2
### В проект, выполненный в предыдущем задании, добавить систему проверки того, что SDK подключен (доступен в режиме онлайн и отвечает на запросы);

 Ход работы: 
 1) 
 2) 

 
## Задание 3
###  1) Произвести сравнительный анализ игровых сервисов Яндекс Игрыи VK Game;
###  2) Дать сравнительную характеристику сервисов,описать функционал;
###  3) Описать их методы интеграции с Unity;
###  4) Произвести сравнение, сделать выводы;
###  5) Подготовить реферат по результатам выполнения пунктов 1-4.
                   
 
## Выводы



## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
