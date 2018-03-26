# 2018-03-29 Python lesson tutor notes

These notes are intended for the tutor as they work through the material, but

<!-- TOC -->

- [TITLE: Building Programs With Python](#title-building-programs-with-python)
- [SECTION 01: Setup](#section-01-setup)
- [SECTION 02: Getting Started](#section-02-getting-started)
- [SECTION 03: Data Analysis](#section-03-data-analysis)

<!-- /TOC -->


# Start the slides

----

## TITLE: Building Programs With Python

----

**SLIDE:** Etherpad

* Please use the Etherpad for the course **DEMONSTRATE LINK**

----

**SLIDE:** Why Are We Here?

- We're here to learn **how to program** (this lesson just happens to be in Python)
- This is a way to **solve problems in your research** through making a computer do work **quickly** and **accurately**
- You'll build **functions** that do specific, defined tasks
- You'll **automate** those functions to perform tasks over and over again (in various combinations)
- You'll **manipulate data**, which is at the heart of all academia
- You'll learn some **file input/output** to make the computer read and write useful information
- You'll learn some **data structures**, which are ways to organise data so that the computer can deal with it efficiently

----

**SLIDE:** XKCD

- The XKCD comic is tongue-in cheek, but there's a **lot of truth in this**

----

**SLIDE** How are we doing this?

- We'll be learning how to program **using Python**
- **Why Python?**
- We need to use *some* language
- Python is **free**, with **good documentation** and lots of books and online courses.
- Python is **widely-used** in academia, and there's lots of support online
- It can be **easier for novices** to pick up than other languages
- **We won't be covering the entire language in detail**
- For those with a bit more experience, note: **we will be using some long-handed ways of doing things to keep them clear for novices**

----

**SLIDE** No, I mean "*How* are we doing this?"

- We'll use **two tools to write Python**
- The **bulk of the course will be in a **text editor**
  - Text editors are part of the **edit-save-execute** cycle, which is how much code is written
- We'll also spend a little bit of time writing code in the `Jupyter` notebook**
  - `Jupyter` is **good for exploring data, prototyping code, data-wrangling, and teaching**
  - However, it's **not so good for writing "production code"** in a general sense
- There are also specialist **integrated development environments (IDEs)** for Python that are extremely useful for developers, but we'll not be using them

----

**SLIDE** Do I need to use `Python` afterwards?

- **No.**
- The lesson and principles are general, we're just teaching in Python
- What you learn here will be relevant in other languages
- If your field or colleagues use another language in preference, **there may be very good reasons for that**, and they **may be able to offer detailed, relevant support and help to you in that language**. This is valuable.
- Language Wars waste everyone's time.

----
**SLIDE** What are we doing?

- We're using **a motivating example of data analysis**
- We've got some data relating to a new treatment for arthritis, and we're going to **explore it.**
- Data represents patients and **daily measurements of inflammation**
- We're going to **analyse** the data
- We're going to **visualise** the data
- We're going to get the computer to do this for us
- **Automation** is key:
  - **fewer human mistakes**
  - easier to **apply to other future datasets**
  - easier to share with others (**transparency**)
- We can also **share our code and results** *via* sites such as GitHub and BitBucket (supplementary information, impact)

----

## SECTION 01: Setup

----

**SLIDE** Setting Up - 1 - **DEMO**

- We want a **neat (clean) working environment**: always a good idea when starting a new project - it helps for when you might want to use `git` to put it under version control, later.
- **Change directory to desktop** (in terminal or Explorer)
- **Create directory** `python-novice-inflammation`
- **Change your working directory** to that directory

```bash
cd ~/Desktop
mkdir python-novice-inflammation
cd python-novice-inflammation
```

----

**SLIDE** Setting Up - 2 - **DEMO**

- We need to **download our data** (and also a little code that can help us)
- **Go to Etherpad in browser** [http://pad.software-carpentry.org/2018-03-29-standrews](http://pad.software-carpentry.org/2018-03-29-standrews)
- **Point out file links** [http://swcarpentry.github.io/python-novice-inflammation/data/python-novice-inflammation-data.zip](http://swcarpentry.github.io/python-novice-inflammation/data/python-novice-inflammation-data.zip)
- **Click on file links to download**
- **Move files** to `python-novice-inflammation` directory
- **Extract files** - this will create a subdirectory called `data` in that folder

- **CHECK WHETHER EVERYONE HAS EXTRACTED THE DATA**

![progress check](images/red_green_sticky.png)

----

## SECTION 02: Getting Started

----

**SLIDE** `Python` in the terminal

- We start the **`Python` console** with the command `python`
  - This should bring up the interactive console
- **Explain** header information
- **Explain** the prompt

```bash
$ python
Python 3.6.3 |Anaconda custom (64-bit)| (default, Oct  6 2017, 12:04:38) 
[GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

- **CHECK WHETHER EVERYONE HAS STARTED THE CONSOLE**

![progress check](images/red_green_sticky.png)

----

**SLIDE** `Python` REPL

- You learned about the REPL (read-evaluate-print-loop) in the shell lesson
  - `Python`'s console implements the REPL
- We can use `Python` like a complex calculator
- **Note the spaces around operators** - good `Python` style

```python
>>> 3 + 5
8
>>> 12 / 7
1.7142857142857142
>>> 2 ** 16
65536
>>> 15 % 4
3
>>> (2 + 4) * (3 - 7)
-24
```

![progress check](images/red_green_sticky.png)

----

**SLIDE** My first variable

- We've seen how to use the REPL
  - To build interesting things, we'll need to store values
  - We need to work with **variables**

- Variables are like **named boxes**
  - An item of data goes into the box
  - When we refer to the box/variable name, we get the **contents of the box**

- We need a **variable name**
- We need **variable contents**

- **Use a real-life example to hand if possible**
- You can think of a variable as a labelled box, containing a data item
  - Here, we have a box labelled `Name` - this is the variable name
  - We've put the value `Samia` into the box

----

**SLIDE:** Creating a variable

- We **assign** a value to a variable with the equals sign: `=`
- Variable **name goes on the left**, **value on the right**
  - Character strings (words etc.) are enclosed in quotes

- After assignment, if we refer to the variable `Name`, we get the value that's in the box, which is: `Samia`

- The **`print()`** function shows the value of a variable
  - **We refer to the name of the variable, and get its contents**



```python
>>> name = "Samia"
>>> name
'Samia'
>>> print(name)
Samia
```

- **CHECK THAT EVERYONE GETS THE CONCEPT/SEES THE NAME**

![progress check](images/red_green_sticky.png)

----

**SLIDE:** Working with variables

- **Lead the students** through the code:

```python
>>> weight_kg = 55
>>> print(weight_kg)
55
```

- Note, we're assigning an integer now (no quotes), but **assignment is the same for all data items**
- Print `weight_kg` to see its value
- **Variables can be substituted by name wherever a value would go**, in calculations for example

```python
>>> 2.2 * weight_kg
121.00000000000001
```

- People may ask about floating point representations here - an introduction is at [https://docs.python.org/3/tutorial/floatingpoint.html](https://docs.python.org/3/tutorial/floatingpoint.html) - this is on the Etherpad.

- The `print()` function will **take more than one argument**, separated by commas, and print them

```python
>>> print("weight in pounds", 2.2 * weight_kg)
weight in pounds 121.00000000000001
```

- **Reassigning** to the same variable overwrites the old value

```python
>>> weight_kg = 57.5
>>> print("weight in kilograms is now:", weight_kg)
weight in kilograms is now: 57.5
```

- Changing the value of one variable **does not automatically change** the values of other defined variables

```python
>>> weight_lb = 2.2 * weight_kg
>>> print('weight in kilograms:', weight_kg, 'and in pounds:', weight_lb)
weight in kilograms: 57.5 and in pounds: 126.50000000000001
>>> weight_kg = 100
>>> print('weight in kilograms:', weight_kg, 'and in pounds:', weight_lb)
weight in kilograms: 100 and in pounds: 126.50000000000001
```

- Although we changed the value in `weight_kg`, **`weight_lb` did not change** when we did so

----

**SLIDE** Exercise 01 (5min)

- **PUT THE EXERCISE SLIDE ON SCREEN**

**MCQ: put up four colours of sticky notes**

- The solution is `2`

----

**SLIDE** Exercise 03 (5min)

**MCQ: put up four colours of sticky notes**

- The code prints `Hopper Grace`

----

## SECTION 03: Data Analysis

----

**SLIDE** Examine the data

- **SHOW THE TERMINAL ON SCREEN**
- In the terminal (`head` was used this morning)

- **Exit `Python` first!**
  - `Ctrl-D`
  - `quit()`
 
```bash
$ head data/inflammation-01.csv 
```

- **Describe the data**: plain text, csv format
- **Can you tell what the data is?** (i.e. is this good practice for sharing data?)
  - One row per patient
  - One column per day
  - Values separated by commas
- **State that we'll use the `numpy` library** to work with this in Python

----

**SLIDE** `Python` libraries

- Most programming languages have **libraries** (also known as **modules**, or **packages**).
  - **Libraries contain code that's not in the main language** but is useful for something specific - they can define **functions**, **data types**, and whole programs
  - **Libraries add specific functionality to the language** - you import as many as you neeed

- `Python` has libraries for many types of work and operations
  - **In `Python`, we call on libraries with the `import` statement**, when we need them
  - Importing a library is like getting a new piece of equipment out of the locker and onto the lab bench

- **Import and describe libraries**

```python
>>> import numpy
```

* `numpy` is a library that provides functions and methods to **work with arrays and matrices**, such as those in your dataset
