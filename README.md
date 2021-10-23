# Кросс-корреляция и нахождение объектов на изображении

Используя двумерную кросс-корреляцию (свертку) найдите шаблон на изображении.

## Часть 1. Кросс-корреляция (под соусом "возьмись уже за дело, товарищь!")

1. (*Опционально*) Реализуйте функцию `cross_correlation(I, K)` в наивной форме при помощи вложенных циклов:
    - в качестве входных данных функция принимает две матрицы - изображение `I` и ядро `K`;
    - допущение: ядро по размерности симметричное  и нечетное (например, 3x3 или 11x11);
    - на выходе должно быть изображение - результат применения кросс-корреляции;
    - выходное изображение должно быть одинакового размера с исходным `I` (незатронутые границы сделайте черными или белыми).

2. Самостоятельно найдите и используйте возможности языка программирования (библиотеки) 
для реализации функции кросс-корреляции `cross_correlation_alt(I, K)`:
    - в качестве входных данных функция принимает две матрицы - изображение `I` и ядро `K`;
    - примечание: ядро может иметь практически любые нечетные размеры (например, 43x51);
    - выходное изображение должно быть одинакового размера с исходным `I` (незатронутые границы сделайте черными или белыми).
    
## Часть 2. Задание шаблона для поиска (aka bounding box)

1. Реализуйте функцию `bounding_box(I, top_left_x, top_left_y, bottom_right_x, bottom_right_y)`, которая
    - возвращает прямоугольный участок изображения в виде еще одного изображения;
    - на вход функция принимает левый верхний и правый нижний угол прямоугольника.
    
2. Постарайтесь вручную подобрать коордианты так, чтобы вычленить какой-либо объект на изображении.

## Часть 3. Поиск шаблона на изображении

Дальше на английском ...

Cross-correlation can be used to look for templates in the images.

### 1. Implement "find the template" on the shelf fucntionality using cross-correlation.

`Note!` The template is located in the 1st row of the shelf (the 2nd element from the left).

**Question.** Is it able to detect the template correctly?

---

<p align="center">
  <img src="figures/shelf.png">
  <p align="center">
    <b>Figure 1.</b>
    <i>Shelf (with cereals for a good breakfast)</i>
  </p>
</p>

<p align="center">
  <img src="figures/template.jpg">
  <p align="center">
    <b>Figure 2.</b>
    <i>Template (cereals)</i>
  </p>
</p>

### 2. Implement zero-mean cross-correlation

Compute and subtract the mean value of the template so that it has zero mean.

### 3. Modify the algorithm for cases of a variable light conditions 

Implement a `norm_cross_correlation` function - normalize the pixels of the image and template at every step before comparing them).

Check the result on the dark shelf image.


<p align="center">
  <img src="figures/dark%20shelf.jpg">
  <p align="center">
    <b>Figure 3.</b>
    <i>Dark shelf (everything has its dark side)</i>
  </p>
</p>

## Общие рекомендации
- за помощью можно обращаться к друг другу и даже работать вместе;
- в папке [demo](demo) есть примеры ноутбуков и кода на Matlab. 
