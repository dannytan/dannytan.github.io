---
layout: essay
type: essay
title: Do You Even Code?
date: 2017-02-08
labels:
  - Software Engineering
  - Coding Standards
  - ESLint
  - IntelliJ IDEA
---

## Bad Code

<img class="ui tiny left circular floated image" src="../images/ESLint.png">

What is considered 'bad code'? Is it code with improper indenting and whitespace? Is it code without enough commenting? Too much commenting? Or, maybe it's code with vague or misleading variable names. There are many parts to a program structure that can create 'bad code' if written improperly. As someone relatively new to computer programming, coding standards, or coding conventions, have not been as stressed compared to actually getting the code to compile. However, I believe following certain guidelines when writing code is important for many reasons. Following coding standards not only makes the code look cleaner, but also improves its readability for others to easily understand the code. This makes group work much more efficient. If all members write following the same standards, the code is consistent, which also makes maintenance easier, too.

## Tools for the Tool Belt

Recently, I was introduced to a tool developers use to catch and correct violations to coding standards. Specifically, I've been using ESLint and the AirBnB JavaScript style guide within the IntelliJ IDEA integrated development environment. My initial reaction to using ESLint was that it is very easy to find, understand, and fix the error shown. A clear red marking indicates an error, hovering over the mark explains the error, and a green check mark is displayed when all the style errors are corrected. So far, I think this tool is extremely useful for creating clean, consistent code. My experience with ESLint has convinced me to use other linting tools for all future projects, regardless of the programming language I decide to use.

## RIP++

Although ESLint has proven to be very useful, there are some code style violations I don't think should be errors. For instance, increment and decrement operators, `++` and `--`, are not allowed by ESLint and the AirBnB JavaScript style guide. Instead, the `+=` operator is suggested to be used. I don't completely understand why this isn't proper code. The purpose of coding standards is to improve readability. Every programmer should know simple increment and decrement operators and what they do. So why are they not allowed? Another example would be the "no-restricted-syntax" error, which flags any use of `for...in` and `for...of` statements. To me, these types of loops are useful and easy to understand. However, I will no longer be able to use them as long as I use ESLint and the AirBnB JavaScript style guide. So far, I've only written small and simple programs using these tools, so I'm sure there are more restricted statements and operators I will come across. However, once I start producing larger and more complex programs within a group, coding up to standard will be the glue that holds everything together.

<img class="ui image" src="../images/tabs_spaces.jpg">
