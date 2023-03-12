# Code Exercise: Number of valid letter combinations

This problem was asked to a friend of mine by salesforce. 

Why is it special to me?<br>
I figured out how to solve it by trying to teach her how to solve it. This has never happened before.

## Problem Description

Given that each integer has a mapping onto A-Z on the alphabet, what are the number of valid combinations of letters we can form out of a given sequence of integers?

Example:
- 101 --> JA --> 1 valid combo
- 1012 --> JAB, JL --> 2 valid combos
- 306 --> 0 valid combos


```python

def recursive_letter_counting(number):
    global combos
    if number=='':
        combos+=1
    else:
        if len(number)>0 and int(number[0]) in range(1,27):
            recursive_letter_counting(number[1:])
        if len(number)>1 and int(number[0:2]) in range(1,27) and int(number[0]):
            recursive_letter_counting(number[2:])
            
def count_combos(n):
    global combos
    n = str(n)
    combos=0
    recursive_letter_counting(n)
    return combos
            

```


```python
count_combos(1112)
```
5

```python
count_combos(100)
```
0

```python
count_combos(11)
```
2

```python
count_combos(101)
```
1
