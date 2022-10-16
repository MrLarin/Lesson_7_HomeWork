# Lesson_7_HomeWork
// Задача 47.Задайте двумерный массив размером m×n,
//заполненный случайными вещественными числами.
/*
m = 3, n = 4.

0,5 7 -2 -0,2

1 -3,3 8 -9,9

8 7,8 -7,1 9
*/
```
int m, n;
m = 3;
n = 4;
double[,] Array2 = new double[m, n];
for (int i = 0; i < m; i++)
{
    for (int j = 0; j < n; j++)
    {
        double S = new Random().NextDouble() * 30 - 10;  // вещесьвенные числа сначала присваиваются переменной
        Array2[i, j] = Math.Round(S, 2); // затем переменная присваивается элементу
        Console.Write($"{Array2[i, j]} "); //Math.Round(S, 2)- округляет до знаков после запятой(в данном случае до 2)
    }
    Console.WriteLine();
}
```

// Задача 50. Напишите программу, которая на вход принимает позиции элемента
// в двумерном массиве, и возвращает значение этого элемента или же указание,
// что такого элемента нет.
/*
Например, задан массив:

1 4 7 2
5 9 2 3
8 4 2 4
17->такого числа в массиве нет
*/
```
int m = 3;
int n = 4;
int[,] array1 = FillPrintArray(m, n);

int i, j;
Console.Write($"Введите позицию элемента: ");
int.TryParse(Console.ReadLine()!, out i);
j = i % 10;
i = i / 10;

if (i > m && j > n || i < 0)
    Console.Write($"Вы вышли за пределы массива");
else
{
    Console.Write($"{array1[i, j]} ");
    Console.ReadLine();
    Console.Write($"Позиция Элемента: {i}, {j} ");
}
```
// Задача 52. Задайте двумерный массив из целых чисел.
// Найдите среднее арифметическое элементов в каждом столбце.
/*
Например, задан массив:
1 4 7 2
5 9 2 3
8 4 2 4
Среднее арифметическое каждого столбца: 4,6; 5,6; 3,6; 3.
*/
```
int m = 3;
int n = 4;
int[,] array1 = FillPrintArray(m, n);
for (int j = 0; j < n; j++)
{
    int sum = 0;
    for (int i = 0; i < m; i++)
    {
        sum += array1[i, j];
    }
    Console.Write($"Ср. Арефметическое {j + 1} столбца: {(double)sum / m}");
    Console.WriteLine();
}
```
// Метод с возврвтом создания и вывода двумерного массива
```
int[,] FillPrintArray(int _m, int _n)
{
    int[,] _Array = new int[_m, _n];
    for (int i = 0; i < _m; i++)
    {
        for (int j = 0; j < _n; j++)
        {
            _Array[i, j] = new Random().Next(0, 10);
            Console.Write($"{_Array[i, j]} ");
        }
        Console.WriteLine();
    }
    //Console.WriteLine($"{_Array[0, 3]}"); //для проверки решения второй задачи
    return _Array;
}
```