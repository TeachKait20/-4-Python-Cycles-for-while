# -6-Python-Cycles-for-while
## Циклы в Python

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/car.gif?raw=true" width="350">

В любой игре где персонаж двигается постоянно или какое-то время нужен цикл. Или, например, программа с видеонаблюдением, которая постоянно обрабатывает кадры в реальном времени, тоже нуждается в цикле. Такие задачи требуют непрерывного выполнения кода для обновления состояния персонажа в игре или анализа новых кадров с камеры. <br>

**Циклы в Python** — это конструкции, которые позволяют повторять блок кода несколько раз, что упрощает выполнение задач, требующих многократного выполнения одинаковых или схожих операций. В Python есть два основных типа циклов: `for` и `while`.

**Итерирование** — это процесс последовательного прохода по элементам коллекции (список, строка, множество, словарь и т.д.) с использованием цикла. Основное преимущество итерирования заключается в простоте и удобстве обработки данных внутри таких структур. (Итерирование = повторение)

## Дополнительные опреаторы для циклов

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/city.gif?raw=true"  width="350">

В Python существуют дополнительные операторы, которые помогают управлять циклом и изменять его стандартное поведение. Основные из них — `break`, `continue`, и `else`. Эти операторы можно использовать как с `for`, так и с `while` циклами.

* `break` - используется для немедленного завершения цикла.
* `continue` - используется для пропуска текущей итерации и перехода к следующей.
* `else` - выполняется, когда цикл завершает все свои итерации без прерывания (`break`). Если цикл завершился с помощью `break`, блок `else` пропускается.

Все эти операторы будут рассмотрены в примерах далее.

## Цикл `for`

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/keyboard.gif?raw=true" width="350">

Цикл `for` используется для перебора элементов в последовательностях (списки, строки, кортежи, множества, словари) или других итерируемых объектов. <br>
Цикл `for` можно использовать в двух конструкциях: с `range` и без.

### Применение range в цикле `for`

Функция `range()` создаёт последовательность чисел, которую можно использовать в цикле `for`. Чаще всего она применяется, когда нужно выполнить итерацию определённое количество раз или создать числовую последовательность.

Синтаксис: `for x in range(start, stop, step)`
* `x` - итерируемая переменная
* `start` (начало) — начальное значение последовательности (включительно). Если этот параметр не указан, range по умолчанию начинается с 0.
* `stop` (конец) — конечное значение последовательности (не включительно). Цикл завершится, когда значение достигнет или превысит `stop`.
* `step` (шаг) — шаг между значениями в последовательности. Если не указан, по умолчанию `step = 1`. Шаг может быть положительным или отрицательным.

При отрицательном шаге, можно развернуть выполнение цикла в обратную сторону.
<br><br>
**Пример 1 ------------------------------------------------------------------**
<br> <br>

```python
for i in range(3): 
    print(i)
```
Здесь итерируемая переменная `i` последовательно принимает значения 0, 1, и 2. Может иметь любое название.
<br> <br>
**Пример 2 ------------------------------------------------------------------**
<br> <br>
Таким образом, можно задать количество повторений цикла:
```python
steps = 9

for x in range(steps):
    print(f"Черепашка сделала {x} шагов")
```
Так и пользователь может ввести количество итераций в `int(input())`
<br><br>
**Пример 3 ------------------------------------------------------------------**
<br> <br>
Здесь пользователь установит сколько раз сработает цикл:
```python
num = int(input("Введите число повторений: "))

print(f"Цикл сработает {num} раз")
for i in range(num):
    print(i)
```
Счёт всегда начинается с 0, но если необходимо другое число, можно сделать следующее:
```python
num = int(input("Введите число повторений: "))

print(f"Цикл сработает {num} раз")
for i in range(1, num+1):
    print(i)
```
Так как счёт идёт с 0, то конечное число не включительно. Поэтому, чтобы всё было корректно, увеличим крайний диапазон на единицу или если мы заранее не знаем числа, просто напишем +1. <br> 
Ещё можно добавить шаг исполнения:
```python
num = int(input("Введите число повторений: "))

print(f"Цикл сработает уже не {num} раз")
for i in range(1, num+1, 2):
    print(i)
```
Теперь цикл будет выполняться через одну итерацию, благодаря шагу 2 в `range`.

### Примеры, когда range не используется

Функция range не всегда подходит, особенно когда требуется перебор объектов, отличных от числовых последовательностей.

Синтаксис: `for x in iterable`

* `x` — итерируемая переменная, которая на каждой итерации принимает значение текущего элемента из итерируемого объекта (`iterable`).
* `iterable` — итерируемый объект, по которому происходит проход. Это может быть список, строка, кортеж, множество, словарь или любой другой объект, поддерживающий итерирование.

Цикл for без range позволяет работать напрямую с элементами коллекций, что упрощает работу с данными и позволяет использовать элементы без необходимости отслеживания их индексов.
<br> <br>
**Пример 1 ------------------------------------------------------------------**
<br> <br>
Рассмотрим перебор всех элементов в списке `fruits`:
```python
fruits = ["apple", "banana", "cherry"]

for char in fruits:
    print(f"Current fruit: {fruit}")
```
В этом примере:
* `fruits` — итерируемый объект (список).
* `char` — итерируемая переменная, которая принимает значение каждого элемента списка fruits по очереди: сначала "apple", затем "banana", и потом "cherry". Она может иметь любое название.
* На каждой итерации цикла `fruit` выводится на экран.

<br>**Пример 2 ------------------------------------------------------------------**
<br> <br>
Итерирование по строке:
```python
text = "Hello"
for char in text:
    print(char)
```
Итерируемая переменная `char` последовательно принимает значения "H", "e", "l", "l", "o".
<br> <br>
**Пример 3 ------------------------------------------------------------------**
<br> <br>
Мы можем легко обойти все элементы структур и найти нужные из них или рассортировать. Например:
```python
numbers = [1, 2, 3, 4, 5, 6]

for x in numbers:
    if x % 2 == 0:
        print(f"{x} - чётное число")
    else:
        print(f"{x} - нечётное число")
```
Так можно перебирать и сортировать большие данные.

### Работа цикла `for` с дополнительными операторами 

Дополнительные операторы `break`, `continue`, и `else` помогают управлять выполнением цикла, изменяя его стандартное поведение.
<br> <br>
**Пример 1 ------------------------------------------------------------------**
<br> <br>
Оператор `break` немедленно завершает выполнение цикла, игнорируя оставшиеся итерации. Он полезен, когда нужно прервать цикл по достижении определённого условия.
```python
numbers = [1, 2, 3, 4, 5, 6, 7, 8]

for num in numbers:
    if num == 5:
        print("Найдено число 5, завершаем цикл.")
        break
    print(num)
```
Когда использовать `break` в `for`:

* Когда необходимо прекратить выполнение цикла при нахождении нужного элемента.
* Для оптимизации, чтобы избежать ненужных итераций после достижения цели.

<br>**Пример 2 ------------------------------------------------------------------**
<br> <br>
Оператор `continue` используется для пропуска текущей итерации и перехода к следующей. Он игнорирует оставшийся код в текущей итерации, но не завершает весь цикл.
```python
for i in range(10):
    if i % 3 == 0:
        continue  # Пропустить числа, делящиеся на 3
    print(i)
```
Когда использовать `continue` в `for`:

* Когда нужно пропустить определённые элементы в процессе итерации.
* Полезно при фильтрации данных, когда определённые условия не должны выполнять основной код итерации.

<br>**Пример 3 ------------------------------------------------------------------**
<br> <br>
Блок `else` сработает после завершения всех итераций цикла, если выход из цикла не произошёл через `break`. Это удобно для выполнения действий по завершении цикла, когда все элементы успешно обработаны.
```python
numbers = [1, 2, 3, 4]

for num in numbers:
    print(f"Проверяем: {num}")
    if num == 10:
        print("Найдено число 10.")
        break
else:
    print("Число 10 не найдено.")
```
Когда использовать `else` в `for`:

* Для выполнения кода, если цикл завершился без прерываний.
* Полезно при проверке условий и выдаче результата после завершения работы цикла.

### Функция `enumerate` для цикла `for`

Например, нам надо поработать именно с индексами списка, найти: первый элемент, промежуточные и последний:

```python
# проверка элементов по индексу

numbers = [0, 1, 2, 3, 4, 5]

for x in numbers:
    if x == numbers[0]:
        print(f"{x} - Первый элемент.")
    if x == numbers[-1]:
        print(f"{x} - Последний элемент.")
    else:
        print(f"{x} - Промежуточный элемент.")
```
Будет работать, но если необходимо рассортировать элементы по индексам, такой метод не подойдёт. <br><br>
Функция `enumerate()` используется для перебора элементов и их индексов в итерируемых объектах, таких как списки, строки или кортежи. <br><br>
Синтаксис: `enumerate(iterable, start=0)`
* `iterable` — итерируемый объект (список, строка, кортеж и т. д.), который будет перебран.
* `start` — начальное значение индекса (по умолчанию 0). Этот параметр указывает, с какого числа начинать счёт индексов.

<br>**Пример 1 ------------------------------------------------------------------**
<br> <br>
```python
fruits = ["apple", "banana", "cherry"]

for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")
```
Как в этом примере работает `enumerate`:
* Переменная `index` получает текущий индекс элемента из итерируемого объекта.
* Переменная `fruit` принимает значение текущего элемента из списка `fruits`.
* На каждой итерации цикл `for` выводит индекс и соответствующий элемент списка.

<br>**Пример 2 ------------------------------------------------------------------**
<br> <br>
```python
fruits = ["apple", "banana", "cherry"]

for index, fruit in enumerate(fruits, start=1):
    print(f"{index}: {fruit}")
```
Использование с изменением начального индекса. Теперь нумерация индексов начинается с 1.
<br><br>
**Пример 3 ------------------------------------------------------------------**
<br> <br>
```python
word = "Python"

for index, letter in enumerate(word):
    print(f"Буква {letter} имеет индекс {index}")
```
Индексы в строке.
<br><br>
**Пример 4 ------------------------------------------------------------------**
<br> <br>
Пример того, как можно использовать функцию:
```python
fruits = ["apple", "banana", "cherry", "orange"]

for index, fruit in enumerate(fruits, start=1):
    if index % 2 == 0:
        print(fruit)
```
Проверка индексов и вывод только чётных.

## Цикл `while`

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/coding.gif?raw=true" width="350">

Цикл `while` выполняет блок кода до тех пор, пока условие остаётся истинным. Этот цикл полезен, когда количество итераций неизвестно заранее и зависит от определённых условий.

Синтаксис: `while mode` 
* `mode` - условие цикла. 

### Конструкция `while` с локальным счётчиком

Цикл `while` с локальным счётчиком часто используется, когда нужно контролировать количество итераций или изменять условие выполнения цикла на основе локальной переменной. <br><br>
**Локальный счётчик** — это переменная, которая отслеживает количество выполненных итераций или используется для изменения состояния в цикле `while`.
<br> <br>
**Пример 1 ------------------------------------------------------------------**
<br> <br>
```python
count = 0
while count < 5:
    print(f"Итерация {count}")
    count += 1
```
В этом примере:

* `count` инициализируется значением 0.
* Цикл выполняется, пока `count` меньше 5.
* На каждой итерации значение `count` выводится на экран, затем `count` увеличивается на 1.

Таким образом, цикл закончит выполнение, на этапе `count = 4`
<br><br>
**Пример 2 ------------------------------------------------------------------**
<br> <br>
```python
c = 10

while c != 0:
    print(f"c = {c}")
    c -= 1
```
Этот код выполняет цикл `while`, который работает, пока значение переменной c не станет равным 0.

### Конструкция `while True`

Конструкция `while True` — это одна из наиболее распространённых форм цикла `while`, которая используется для создания бесконечных циклов. Такой цикл продолжает выполняться до тех пор, пока не будет встречен оператор `break` или не возникнет внешнее условие для завершения программы (например, ошибка или закрытие программы пользователем).
<br><br>
**Пример 1 ------------------------------------------------------------------**
<br> <br>
```python
number = 0

while True:
    number += 1
    print(number)
```
**Важно!** Данная программа будет работать бесконечно, пока это позволяет ресурс компьютера. 
<br><br>
**Пример 2 ------------------------------------------------------------------**
<br> <br>
Лучше использовать дополнительные операторы для циклов, исходя из условий:
```python
while True:
    print("2 + 2 = ?")
    answer = input("введите ответ: ")
    if answer == "4":
        print("Вы ответили верно!")
        break
    else:
        print("Пока неправильно! Попробуйте ещё раз.")
```
В данном случае, цикл прекратиться тогда, когда пользователь даст правильный ответ.
<br><br>
**Пример 3 ------------------------------------------------------------------**
<br> <br>
Пример того, как можно построить цикл для главного героя компьютерной игры:
```python
hp_hero = 100  # жизни героя
is_alive = True  # герой жив

enemy_damage = 25  # урон врагов по герою

while is_alive:  # цикл продолжается, пока герой жив
    print(f"У героя {hp_hero} здоровья")
    hp_hero -= enemy_damage
    
    if hp_hero <= 0:  # проверка, что герой жив
        is_alive = False
```
Конечно, мы могли построить цикл без дополнительных переменных или как в прошлых примерах на `while True`. Но так как игра куда масштабнее, чем несколько строчек кода, эти данные могут пригодиться где-то ещё.

## Частые ошибки и табуляция в циклах

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/sleep.gif?raw=true" width="350">

Работа с циклами может привести к ряду распространённых ошибок, которые могут вызвать неожиданные результаты или привести к бесконечным циклам. Ниже 👇 перечислены самые частые ошибки при работе с циклами и способы их избежать.

### 1. Бесконечные циклы

Бесконечный цикл возникает, когда условие выхода из цикла никогда не выполняется, либо оператор `break` не срабатывает.

Пример:
```python
i = 0
while i < 5:
    print(i)
    # i += 1 забыто
```
Всегда проверяйте, что условие цикла изменяется внутри цикла и что оно корректно завершится при заданных параметрах.

### 2. Неправильное использование `range()`

Неправильная работа с диапазоном в `for` циклах может привести к неверному количеству итераций или ошибкам.

```python
for i in range(5, 1):  # Шаг по умолчанию +1, поэтому цикл не выполнится
    print(i)
```
Всегда проверяйте корректность указания границ и шага.

### 3. Ошибки при работе с индексами

Выход за границы списка или попытка обращения к несуществующему элементу часто приводит к ошибке `IndexError`.

```python
numbers = [1, 2, 3]

for i in range(4):  # Попытка доступа к несуществующему индексу 3
    print(numbers[i])
```
Используйте `len()` для определения длины списка и правильного указания диапазона.

### 4. Неправильное использование `break` и `continue`

Использование `break` и `continue` не в той ситуации, когда это требуется, приводит к пропуску итераций или к преждевременному завершению цикла.

```python
for i in range(5):
    if i == 3:
        break  # Завершает цикл, пропуская числа после 3
    print(i)
```
Убедитесь, что условия для `break` и `continue` правильно установлены и соответствуют логике программы.

### 5. Ошибки с вложенными циклами

Вложенные циклы часто приводят к путанице в логике и неправильной работе программы.

```python
for i in range(3):
    for j in range(3):
        if i == 1:
            break  # Завершает только внутренний цикл, а не внешний
        print(i, j)
```
Чётко определяйте, какой цикл нужно завершить, и используйте условия с осторожностью.

### Неправильная табуляция

Как вы могли заметить, табуляция есть не только в условиях, но и в циклах и из-за пересечений её становится ещё больше.

```python
for i in range(5):
    print(i)  # Этот код находится в цикле и будет выполнен 5 раз
print("Цикл завершён")  # Этот код не в цикле, он выполнится один раз
```
Или чуть сложнее:
```python
# Пример с использованием цикла for и условий внутри него
numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

for num in numbers:            # Цикл перебирает каждый элемент списка
    if num % 2 == 0:           # Проверка, является ли число чётным
        print(f"{num} — чётное число")   # Выполнится, если условие истинно
    else:
        print(f"{num} — нечётное число") # Выполнится, если условие ложно
```
Следите за одинаковым количеством пробелов в блоках кода, особенно при редактировании. Используйте средства разработки, которые автоматически выравнивают отступы (например, PyCharm, VS Code).

## Задания для самостоятельного выполнения

<img src="https://github.com/TeachKait20/NoneCode/blob/main/cycles+for+while/window.gif?raw=true" width="350">

**Задание 1**

Дан список имён:
`names = ["Richard", "Igor", "Jonathan", "Alice", "Mary", "Bonnie"]`

С помощью цикла `for` переберите все имена и выведете в строку: Hello Name!

Пример выходных данных: <br>
![image](https://github.com/user-attachments/assets/fe9de1a4-df51-4c70-b015-ed50f17cb2a2)

**Задание 2**

`phrase = "I'm learning cycles."`

С помощью цикла `for` выведете `phrase` 10 раз.

**Задание 3**

Есть список остановок поезда:
`stations = ["Малиновка", "Рябиновка", "Суслово", "Дрожжино", "Звягино"]`

1. С помощью цикла `for` переберите все остановки и выведете их в консоль в виде: Поезд на станции: NameStation
2. С помощью условия добавьте проверку, если в списке остановка последняя, то добавьте сообщение: Конечная!

Пример выходных данных: <br>
![image](https://github.com/user-attachments/assets/8cc4a406-11cd-490e-8f52-75aebd863d4d)

**Задание 4**

Дан список:
`shop = ["Laptop", "Smartphone", "Watch", "Tablet", "Headphones"]`

* Напишите цикл `for`, который проходит по всем элементам списка shop.
* Если товар в списке равен "Laptop", выведите сообщение "I'm buying this.".
* Если товар не "Laptop", то ничего выведите: "I don't need it."

**Задание 5**

У вас есть список задач на неделю с приоритетами. Каждой задаче нужно присвоить порядковый номер и вывести её в формате с указанием приоритета. Задачи, которые помечены как "Важная", должны выводиться с восклицательным знаком !, а остальные задачи просто с номером.

`tasks = ["Сдать проект (Важная)", "Сходить в магазин", "Позвонить врачу (Важная)", "Убраться в комнате", "Подготовить отчёт"]`

* Используйте `enumerate()` в цикле `for` для нумерации задач, начиная с 1.
* Если задача помечена как "Важная", добавьте ! после номера задачи. (Для этого можно использовать оператор членства и проверить строки `"abc" in "abcdefg"`)
* Выводите задачи в формате: Номер: Задача.
* Если задача важная, добавьте к её номеру знак !.

Выходные данные: <br>
![image](https://github.com/user-attachments/assets/314188c8-ef6d-432f-b0b2-90a56216dee1)

**Задание 6**

Напишите программу, которая сначала запрашивает у пользователя, сколько чисел он хочет ввести, а затем просит ввести эти числа по одному. После ввода всех чисел программа должна вывести:

* Список всех введённых чисел.
* Сумму всех чисел.

Задание решается с помощью цикла `for`. Сумму можно посчитать используя переменную, находящуюся вне цикла, к которой будет прибавляться значение после каждой итерации.

Выходные данные: <br>
![image](https://github.com/user-attachments/assets/73a46137-aa2f-44af-b28c-280da22a4931)

**Задание 7**

Постройте цикл `while` таким образом, чтобы он сработал 10 раз и вывел каждую итерацию. Цикл работает от локального счётчика.

Пример выходных данных: <br>
![image](https://github.com/user-attachments/assets/68201711-e3eb-4a2a-bb53-74960bdc987d)

**Задание 8**

Напишите программу, которая будет управлять движением персонажа в зависимости от команд, введённых пользователем. Программа должна постоянно ждать ввод команды и выводить соответствующее действие. Команды управления:

* `w` — персонаж идёт вперёд.
* `a` — персонаж идёт влево.
* `s` — персонаж идёт назад.
* `d` — персонаж идёт вправо.
* `stop` — завершить программу.

1. Программа должна работать бесконечно, пока пользователь не введёт команду `stop`.
2. На каждую команду (`w`, `a`, `s`, `d`) программа должна выводить соответствующее действие персонажа.
3. Если введена команда `stop`, программа должна завершить выполнение с сообщением об остановке.
4. Если введена неизвестная команда, вывести сообщение: "Неизвестная команда! Попробуйте снова."

Пример выходных данных: <br>
![image](https://github.com/user-attachments/assets/4f8e98f7-670e-4f68-9d52-0bafe2c8468a)

