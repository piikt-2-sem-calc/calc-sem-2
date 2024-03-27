# calc-sem-2
Для загрузки решений ргр по матанализу 2024, весенний семестр

# ATTENTION
Перед загрузкой результата по практическому заданию, внимательно прочитайте рекомендации ниже
* вам нужно создать приватный репозиторий (название репы - ваши фамилия и имя на английском, она создается внутри данной организации) и добавить в него как коллаборатора меня (gh: Alerrom или mail: alex2002andr@mail.ru)
* перед выполнением практического задания, создайте отдельную от main ветку
* решение нужно добавить через pull-request (merge делать до аппрува проверяющего НЕЛЬЗЯ!)
* если возникают трудности по технической части задания (работа с git, github, не получается создать код), то задавайте свои вопросы в чат или в лс


# Условие задания 3

## Аналитический этап

В рамках данного задания необходимо 

- составить верхнюю и нижнюю суммы Дарбу, доказать интегрируемость функции (разбиение использовать такое, что его мелкость будет стремиться к 0)
- для интеграла Римана данной функции по данному промежутку составить интегральную сумму (можно использовать результат из предыдущего пункта), найти предел этой суммы
- сравнить полученный результат с ответом по формуле Ньютона-Лейбница

## Практический этап

Напишите программу (рекомендуемый язык: python 3+, java), вычисляющую интеграл

- разбейте промежуток $[a, b]$ на $n$ равномерных частей (для желающих рекомендуем сделать поддержку неравномерного разбиения)
- проверьте, что ваше разбиение удовлетворяет условию, что мелкость стремится к нулю
- составить интегральную сумму для вычисления криволинейной трапеции с высотой$[x_{i-1}, x_i]$, использовать следующие подходы:
    - Метод прямоугольников: $s_i = f(\xi_i)\cdot \Delta x_i$, где $\xi_i$ выбирается как самая левая, самая правая или случайная точка на каждом промежутке $[x_{i-1}, x_i]$, здесь и далее $\Delta x_i = x_i - x_{i-1}$
    - Метод трапеций:  $s_i = (f(x_{i-1})+f(x_i))\cdot\dfrac{\Delta x_i}{2}$
    - Метод Симпсона:  $s_i = \left(f(x_{i-1})+4f\left(\dfrac{x_i+x_{i-1}}{2}\right)+f(x_i)\right)\cdot\dfrac{\Delta x_i}{6}$
- для указанной в вашем варианте и любом другом соседнем варианте функции на данном промежутке проверьте, что ответ, полученный в результате применения всех методов совпадает с тем, что вы получили в аналитическом этапе задания
- проведите измерения для мелкости $\Delta x_i, \dfrac{\Delta x_i}{2}, \dfrac{\Delta x_i}{4}, \dfrac{\Delta x_i}{8}, \dfrac{\Delta x_i}{16}$ при фиксированной $\Delta x_i$
- постройте график зависимости отклонения значения интеграла от величины шага ([MSE](https://en.wikipedia.org/wiki/Mean_squared_error), [MAE](https://en.wikipedia.org/wiki/Mean_absolute_error))
    - $MAE = \dfrac{\left|I-I_k\right|}{n}$
    - $MSE = \dfrac{\left(I-I_k\right)^2}{n}$
    - в обоих случаях $I$ - значение исходного интграла,  $I_k$ - интегральная сумма, полученная при некотором конечном разбиении
- сделайте выводы об эффективности методов (для полого анализа рекомендуется изменять не только функцию, но и сам промежуток), опираясь на следующие параметры:
    - сложность вычислений
    - время вычислений
    - точность вычислений

**Важно: формат ввода данных определяется самостоятельно! Единых стандартов нет, потому что задача будет проверяться не на тестах, а при защите. Старайтесь писать код с возможностью расширения и использования паттернов.**
