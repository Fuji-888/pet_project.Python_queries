# Базовый Python

## Добавил некоторые задачки, которые я решил, из курса "Базовый Python" от платформы Simulativ. Все добавлять не стал, потому что этим никого не удивить.

## Выбрал этот курс потому, что в первую очередь автор курса и преподаватель рассказывал про Python уже с привязкой к аналитике, рассказывал про задачи, которые он помогает решить в работе, делал отвлечения на свой опыт в аналитике. Так же понравился бекграунд этого человека, что он по отзывам других медийных аналитиков данных "сильный хардовик". 

## Нормальный пет проект пока не делал, потому что пока в процессе знакомства с Pandas и другими фреймворками.
#### Задача 1
 
В кассе имеется ограниченное количество банкнот номиналом 10, 50 и 100. 

Вам дана сумма amount, которую нужно выдать, и количество доступных банкнот каждого номинала. 

Напишите функцию count_banknotes, которая принимает сумму к выдаче amount и доступное количество банкнот каждого номинала (num_100_available, num_50_available, num_10_available). Функция должна возвращать кортеж с минимальным количеством банкнот каждого номинала, которое кассир должен будет выдать.

```python
def count_banknotes(amount, num_100_available, num_50_available, num_10_available ):
 a100 = min(amount // 100, num_100_available)
 a100_ = amount - a100*100 #=50
 a50 = min(a100_ // 50, num_50_available ) 
 a50_ = a100_ - a50*50 # = 0
 a10 = min(a50_ // 10, num_10_available)
 return a100,a50,a10
```

#### Задача 2

Вам дан словарь зарегистрированных на платформе пользователей, где id пользователя - ключ, а значение - его никнейм.

Напишите функцию greeting(), которая будет приветствовать посетителя, опираясь на его id и ник. Если id совпадает с id зарегистрированного пользователя, функция должна вернуть Добро пожаловать, {никнейм}!. Если такого id нет в словаре функция должна поприветствовать пользователя и предложить придумать себе псевдоним - Добро пожаловать, {имя}! Хотите задать никнейм?.

```python
def greeting(user_dict, user_id,**kwargs):
  if not user_dict.get(user_id):
    return f'Добро пожаловать, {list(kwargs.values())[0]}! Хотите задать никнейм?')
  else:
    return f'Добро пожаловать, {user_dict.get(user_id)}!')
```

#### Задача 3

Напишите функцию order_total(), которая вычислит полную стоимость заказа клиента. 

Каждый заказ состоит из списка товаров, где каждый товар представлен словарем, содержащим название товара, цену и количество. Функция должна принимать список items и возвращать общую стоимость заказа числом. Если список товаров пуст - верните 0.

```python
def order_total(items):
  if not items:
   return 0
  else:
   total = items[0]['price']*items[0]['quantity'] 
   return total +  order_total(items[1:])
```

#### Задача 4

Условие задачи
Дан список чисел ref_list. Начиная с позиции start нужно вставить rep повторений числа num. Если список ref_list короче start, вернуть -1

Задание
Напишите функцию list_insert, которая возвращает список чисел, в который вставлены числа num в количестве rep с позиции start.

Функция list_insert принимает на вход:


исходный список ref_list

числовой номер позиции start

число num

число повторений rep.

```python
def list_insert(ref_list, start, num, rep):
    # напишите свой код ниже
     if start <= len(ref_list) or len(ref_list) == 0:
         l = [num] * rep
         ref_list[start:start] = l
         
         return ref_list
     else:
         return -1
```    

#### Задача 5

Напишите функцию adder(), которая принимает список lst и добавляет все элементы списка в новый список.

Если в списке lst встретится пустая строка, функция должна вернуть кортеж из строки "Есть пустая строка" и получившегося списка. Если изначально переданный список lst пуст - функция должна вернуть "Список пуст".

```python
def adder(lst):
  if not lst:
    return('Список пуст')
  else:
    lst2 = []
    for i in lst:
      if not i:
        return 'Есть пустая строка',lst2
      else:
        lst2.append(i)
    return lst2
```

#### Задача 6

Напишите функцию Quarterly, которая будет возвращать список - суммарные значения за каждый квартал. Первое значение - сумма за первый квартал с января по март, и так далее.

Функция Quarterly принимает на вход monthly - исходный список с числами.

```python
def Quarterly(monthly):
  sumx = []
  for i in range(1,5):
    sumx.append(round((monthly.pop(0) + monthly.pop(0) + monthly.pop(0)),2))
  return sumx 
```

#### Задача 7

Задание
Напишите функцию list_numbers, которая возвращает список чисел от start до stop включительно.

Функция list_numbers принимает на вход целые числа start и stop.

```python
def list_numbers(start, stop):
    
  lst1 = []
  if start < stop:
    while start <= stop:
      lst1.append(start)
      start += 1
  else:
    while start >= stop:
      lst1.append(start)
      start -= 1
  return lst1 
```
