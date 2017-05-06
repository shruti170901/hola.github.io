---
layout: page
title: Exercise 1 FizzBuzz
description: This can be your first exercise to practice TDD. It is a good exercise for you to start and give you the real feeling of TDD. Don't feel bad if you couldn't do it well as this happens to everyone who start practicing TDD for the 1st time including myself :)
---

# Exercise 1.1

You are going to write a function "Say" with input of integer and output of string. The function return the integer itself except these numbers:

- Multiples of three, returns "Fizz"
- Multiples of five, returns "Buzz"
- Multiples of three AND five, returns "FizzBuzz"

Here are sample outputs from the input 1 to 15:  
_1  
2  
Fizz  
4  
Buzz  
Fizz  
7  
8  
Fizz  
Buzz  
11  
Fizz  
13  
14  
FizzBuzz  
..._

Please try implement this function in TDD way. Do not look for the solution on the internet before you try on your own. Different developers might come up with different codes.

Once done, check: Does your test code has good readability? Do you need to move around your code or your mouse in order to read your code?

# Exercise 1.2

What if we want to add more logics:

- Multiples of seven, returns "Wow"
- Multiples of three AND seven, returns "FizzWow"
- Multiples of five AND seven, returns "BuzzWow"
- Multiples of three, five AND seven, returns "FizzBuzzWow"

Here are some sample inputs/outputs:  
7 = Wow  
14 = Wow  
21 = FizzWow  
35 = BuzzWow  
105 = FizzBuzzWow  

Does your code has good maintainability? Can you add these logics without touching existing codes?

# Exercise 1.3

What if we want to change some wordings:

- Multiples of three AND five, returns "Transfer"
- Multiples of three AND seven, returns "Thousand"
- Multiples of five AND seven, returns "Foresee"
- Multiples of three, five AND seven, returns "TFS"

Does your code has good maintainability? Can you change these words without touching existing codes?

[Click here to find solution](/tdd/ex01_fizzbuzz_ans.html)