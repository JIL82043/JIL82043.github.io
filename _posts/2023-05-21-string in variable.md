---
layout: single
title:  "String in Variable"
categories: basic
tag: [python, basic, variable, string]
toc: true
author_profile: false
---

### String
: **Sequence, Immutable**

**ASCⅡ** : *Letter - Number Mapping* (8bit = 1byte)


```python
print(ord('H'))
```

    72
    

**Unicode (UTF-8)** : Encoding *a letter → 1~4byte*


```python
x = b'abc'
y = x.decode()
print(x, type(x), y, type(y))
```

    b'abc' <class 'bytes'> abc <class 'str'>
    

> String of Python use Unicode

#### String Creation


```python
a = 'hello world'
b = "hello\nworld"
c = '''hello\tworld'''   # \n, \t : escape string
d = """hello

world"""
print(a)
print(b)
print(c)
print(d)
```

    hello world
    hello
    world
    hello	world
    hello
    
    world
    

#### String Formatting

- [use %](https://docs.python.org/3/library/stdtypes.html#old-string-formatting)


```python
print('안녕하세요? %s' % ('반갑습니다'))   # %s : String in Tuple
print('안녕하세요? %.3f' % (0.12345))   # %f : Float(소수 셋째자리까지) in Tuple
print('안녕하세요? %d' % (12345))   # %d : Int in Tuple
print('안녕하세요? %c' % ('a'))   # %c : Character(단일문자 하나) in Tuple
```

    안녕하세요? 반갑습니다
    안녕하세요? 0.123
    안녕하세요? 12345
    안녕하세요? a
    

- [use {} and .format()](https://docs.python.org/3/library/string.html#formatstrings)


```python
print('웰컴투? {}'.format('파이썬'))
print('원주율? {:>6.2f}'.format(3.141592))   #오른쪽 공백 6칸, Float의 소수 둘째자리까지

temp = 25.5
prob = 80.0
a = '오늘 기온 {}도이고, 비 올 확률은 {}%입니다.'.format(temp, prob)
print(a)

name = 'Annie'
print("Your lucky number is {1}, {0}.".format(name, len(name)*3))
print("Your lucky number is {number}, {name}.".format(name=name, number=len(name)*3))
```

    웰컴투? 파이썬
    원주율?   3.14
    오늘 기온 25.5도이고, 비 올 확률은 80.0%입니다.
    Your lucky number is 15, Annie.
    Your lucky number is 15, Annie.
    

- [use f](https://docs.python.org/3/reference/lexical_analysis.html#f-strings)


```python
name = '펭수'
age = 10
print(f'나의 이름은 {name}입니다. 나이는 내년에 {age + 1}살이 됩니다.')
```

    나의 이름은 펭수입니다. 나이는 내년에 11살이 됩니다.
    

#### String Indexing


```python
a = 'Hello world'

print(a[0])
print(a[10])
print(a[-1])   #마지막 값
print(a[6:10])   #Slicing 6부터 9까지
print(a[:5])   #끝(처음) 생략가능
print(a[::2])   #2글자씩 건너뛰기
```

    H
    d
    d
    worl
    Hello
    Hlowrd
    


```python
a = 'Hello world'

b = 'j' + a[1:]
c = a.replace('h', 'j')

print(b)
print(c)
```

    jello world
    Hello world
    

#### Function Related
[String Method](https://docs.python.org/3/library/stdtypes.html#string-methods)   
<code>TAB</code> → show member function(method)

##### upper / lower / capitalize


```python
'hello World'.upper()
```




    'HELLO WORLD'




```python
'hello World'.lower()
```




    'hello world'




```python
'hello World'.capitalize()
```




    'Hello world'



##### replace


```python
'hello World'.replace('l', 'L')
```




    'heLLo WorLd'



##### strip, lstrip, rstrip


```python
a = '                  01-sample.png  '
print(a.strip())   #whitespace 및 \t, \n도 제거
print(a.lstrip())
print(a.rstrip())
```

    01-sample.png
    01-sample.png  
                      01-sample.png
    

##### split


```python
a = 'Hello world what a nice weather'

print(a.split())   #띄어쓰기 기준
print(a.split('w'))
```

    ['Hello', 'world', 'what', 'a', 'nice', 'weather']
    ['Hello ', 'orld ', 'hat a nice ', 'eather']
    

##### len


```python
a = 'eat banana'
len(a)
```




    10



##### join


```python
'-'.join(['010', '1234', '5678'])
'-'.join('ABCD')
```




    'A-B-C-D'



##### index & find


```python
pets = 'Cats & Dogs'
print(pets.index('&'))
print(pets.index('s'))
# print(pets.index('k'))

fruit = 'banana is a fruit'
pos1 = fruit.find('na')
print(pos1)
pos2 = fruit.find('z')
print(pos2)
pos3 = fruit.find(' ', fruit.find('is'))
print(pos3)
```

    5
    3
    2
    -1
    9
    

##### count


```python
"The number of times e occurs in this string is 4".count('e')
```




    4



##### startswith, endswith


```python
print("Forest".startswith('For'))
print("Forest".endswith('rest'))
```

    True
    True
    

##### isnumeric, isalpha


```python
print("Forest".isnumeric())
print("12345".isnumeric())
print("Forest".isalpha())
print("12345".isalpha())
print("annie is my friend".isalpha())
```

    False
    True
    True
    False
    False
    

##### etc


```python
a = '반갑습니다!'
b = '웰컴 투 파이썬'

print('=====' * 10)
print(b + ', ' + a)

pets = 'Cats & Dogs'
print('Dragons' in pets)
```

    ==================================================
    웰컴 투 파이썬, 반갑습니다!
    False
    
