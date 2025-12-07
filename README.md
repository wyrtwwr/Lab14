# Домашнее задание к работе 14
## Условие задачи

Запись «Сотрудник»:
Фамилия
Имя
Отчество
Пол
Должность
Дата рождения
Вывести данные об инженерах, пенсионного возраста
(мужчинам больше 65-ти лет, женщинам 60).

## 1. Алгоритм и блок-схема
## Алгоритм
```
1. Начало.
2. Объявление size 3;
3. Создание структуры player c полями: char lastname[20];
    char name[20];
    char surname[20];
    char gender[10];
    char position[20];
    int year;;
4. Объявление структуры employee p1[size];
5. i = 0;
   Пока i < size:
     вводим &p1[i].lastname,
     вводим &p1[i].name,
     вводим &p1[i].surname,
     вводим &p1[i].gender,
     вводим &p1[i].position,
     вводим &p1[i].year
     Если ((strcmp(p1[i].gender, "m") == 0 && age > 65 && strcmp(p1[i].position, "Engineer") == 0) ||
            (strcmp(p1[i].gender, "f") == 0 && age > 60 && strcmp(p1[i].position, "Engineer") == 0))
       printf("фамилия: %s; дата рождения: %d.%d.%4d; город: %s; амплуа: %s; кол-во игр: %d; кол-во желтых карточек: %d\n", p1[i].name, p1[i].day, p1[i].manth, p1[i].year, p1[i].city, p1[i].amplua, p1[i].c_plays, p1[i].c_card);
     i++;
6. Конец.
```
   
### Блок-схема

<img width="867" height="830" alt="{52673CCE-CC77-47C6-A51F-F46D6D2F8BD1}" src="https://github.com/user-attachments/assets/9dcbdc05-09f4-49da-8061-6b7e38a4ec66" />


## 2. Реализация программы

```
#define _CRT_SECURE_NO_DEPRECATE
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <locale.h>
#include <string.h>
#define size 3

struct employee {
    char lastname[20];
    char name[20];
    char surname[20];
    char gender[10];
    char position[20];
    int year;
};
typedef struct employee employee;

void main()
{
    setlocale(LC_ALL, "RUS");
    struct employee p1[size];

    for (int i = 0; i < size; i++) {

        printf("Фамилия: ");
        scanf("%19s", p1[i].lastname);

        printf("Имя: ");
        scanf("%19s", p1[i].name);

        printf("Отчество: ");
        scanf("%19s", p1[i].surname);

        printf("Пол: ");
        scanf("%9s", p1[i].gender);

        printf("Должность: ");
        scanf("%19s", p1[i].position);

        printf("Год рождения: ");
        scanf("%d", &p1[i].year);

        int age = 2025 - p1[i].year;

        if (
            (
                strcmp(p1[i].gender, "m") == 0 &&
                age > 65 &&
                strcmp(p1[i].position, "engineer") == 0
                )
            ||

            (
                strcmp(p1[i].gender, "f") == 0 &&
                age > 60 &&
                strcmp(p1[i].position, "engineer") == 0
                )
            )
        {
            printf("Фамилия: %s; \n Имя: %s; \n Отчество: %s; \n Пол: %s; \n Должность: %s; \n Год рождения: %d\n",
                p1[i].lastname,
                p1[i].name,
                p1[i].surname,
                p1[i].gender,
                p1[i].position,
                p1[i].year);
        }
}

```


## 3. Результаты работы программы

```
Фамилия: Ivanov
Имя: Ivan
Отчество: Ivanovitch
Пол: m
Должность: Engineer
Год рождения: 1900
Фамилия: Ivanov;
 Имя: Ivan;
 Отчество: Ivanovitch;
 Пол: m;
 Должность: Engineer;
 Год рождения: 1900
Фамилия:

```


<img width="896" height="324" alt="{02418DCA-F442-453C-8FE3-1A6DFE5D80FC}" src="https://github.com/user-attachments/assets/aecc61ec-a5b2-4213-90e0-c60120f57fff" />
