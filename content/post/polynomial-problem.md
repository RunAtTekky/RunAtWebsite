+++
title = 'Polynomial Problem'
date = 2025-08-31T15:27:28+05:30
draft = false
tags = ['tech', 'dev', 'go']
+++
[Hashira](https://hashira.io/) came to our campus for hiring.

I didn't attend their assessment process coz I forgot to apply ☠️

But I found out that they asked a very interesting problem based on polynomials.

## Problem
### Input
You will be given json input like this:
```json
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}
```

You can also check out their input here ([input format](https://honorable-marimba-e75.notion.site/Hashira-Placements-Assignment-Online-16c880a946cf805f9ab6c3aacd180f8d))

### Explanation
You are given keys.n and keys.k which mean:
- n: number of entries given
- k: number of roots required to solve the equation
- m: k-1, m is the degree of the polynomial

> Basically you are given something like this
>
> aX^m + bX^(m-1) + cX^(m-2) + ..... = y

In each entry you are given:
- x: this is the x you will input in your unknown polynomial
- y: by using the base and value you can figure out the y

### Requirement
You need to find the coefficients of the polynomial.

## Solution
> I solved this problem with [Gaussian Elimination Method](https://www.geeksforgeeks.org/dsa/gaussian-elimination/) which uses [Row Echelon Form](https://en.wikipedia.org/wiki/Row_echelon_form) and Back Substitution

### Steps
- Parsing JSON

- Conversion of bases to get y value

- Create equation using x, y and m

- Create Augmented Matrix using these equations for given entries

- USE Gaussian Elimination Method
    - It converts Augmented Matrix to Row Echelon Form
    - It uses back substitution to find out the variables

> Output: We get the value of variables in a map {a: X, b: X, c: X, ....}

Here is my [GitHub Repo](https://github.com/RunAtTekky/polynomial-problem) for the same
