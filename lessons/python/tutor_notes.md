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

- **WE WANT TO FIND SUMMARY INFORMATION ABOUT INFLAMMATION BY PATIENT AND BY DAY**

----

**SLIDE** `Python` libraries

- Most programming languages have **libraries** (also known as **modules**, or **packages**).
  - **Libraries contain code that's not in the main language** but is useful for something specific - they can define **functions**, **data types**, and whole programs
  - **Libraries add specific functionality to the language** - you import as many as you neeed

- `Python` has libraries for many types of work and operations
  - **In `Python`, we call on libraries with the `import` statement**, when we need them
  - Importing a library is like getting a new piece of equipment out of the locker and onto the lab bench

- There are several repositories that host `Python` packages
  - [`PyPI`](https://pypi.python.org/pypi)
  - [`conda`](https://conda.io/docs/)

- **Import and describe libraries**

```python
>>> import numpy
```

* `numpy` is a library that provides functions and methods to **work with arrays and matrices**, such as those in your dataset

----

**SLIDE** Load data from file

- The `numpy` library gives us a function called **`loadtxt()` that loads tabular data from a file**
- To use a `function` from a `library`, **the format is usually `library.function()`: *dotted notation***
- **`loadtxt()` expects two *arguments* or *parameters*** - values it needs to know to work
- The parameter `fname` takes the **path to the file we want to load**
- The parameter `delimiter` takes the **character that we think separates columns** in that file

```python
>>> numpy.loadtxt(fname='data/inflammation-01.csv', delimiter=',')
array([[ 0.,  0.,  1., ...,  3.,  0.,  0.],
       [ 0.,  1.,  2., ...,  1.,  0.,  1.],
       [ 0.,  1.,  1., ...,  2.,  1.,  1.],
       ..., 
       [ 0.,  1.,  1., ...,  1.,  1.,  1.],
       [ 0.,  0.,  0., ...,  0.,  2.,  0.],
       [ 0.,  0.,  1., ...,  1.,  1.,  0.]])
```

- Here, our function is `numpy.loadtxt()`, and  *Dotted notation* tells us that `loadtxt()` belongs to `numpy`
- `Python` will accept **double- or single-quotes** around strings

----

**SLIDE** Loaded data

- If we don't ask `Python` to do anything with the data, it just loads the data, then shows the data to us.
- The data display is truncated by default - *ellipses* (`...`) show rows and columns that were excluded for space 
- Significant digits are not shown
- **NOTE that integers in the file have been converted to floating point numbers**
- **Ask the learners to assign the matrix to a variable called `data`: MAKE THIS CHANGE IN-PLACE**

```python
>>> data = numpy.loadtxt(fname="data/inflammation-01.csv", delimiter=",")
```

- Now when we execute the cell **we see no output**, but `data` now contains the array, which we can see by **printing the variable**

```python
>>> print(data)
[[ 0.  0.  1. ...,  3.  0.  0.]
 [ 0.  1.  2. ...,  1.  0.  1.]
 [ 0.  1.  1. ...,  2.  1.  1.]
 ..., 
 [ 0.  1.  1. ...,  1.  1.  1.]
 [ 0.  0.  0. ...,  0.  2.  0.]
 [ 0.  0.  1. ...,  1.  1.  0.]]
```

----

**SLIDE** What is our data?

- We've loaded some data, but **what is it?**

```python
>>> type(data)
<class 'numpy.ndarray'>
```

- **`Python` sees our data as a special `type`: `numpy.ndarray`**
- From *dotted notation* we see that `ndarray` belongs to (was defined in) the `numpy` library
- `ndarray` stands for "n-dimensional array" - so this is **an n-dimensional array from the `numpy` library**

----

**SLIDE** Members and attributes

- **Creating our `data` array created a lot of information, too**
- We created **information about the array** called *attributes*
- This information belongs to `data` so is **accessed in the same way as a module function**, through *dotted notation*

```python
>>> print(data.dtype)
float64
>>> print(data.shape)
(60, 40)
```

- `print(data.dtype)` tells us that the **data type for values in the array** is: 64-bit floating point numbers
- `print(data.shape)` tells us that there are **60 rows and 40 columns** in the dataset

----

**SLIDE** Indexing arrays

- We often want to work with subsets of data
  - individual rows and columns
  - subgroups of rows and columns
  - **individual patients** (rows)
  - **individual days** (columns)

- Arrays are indexed by *row* and *column*, using *square bracket* notation
- To get a single element from the array, **index using *square bracket* notation** - row first, then column

```python
>>> data[10, 10]
5.0
```

* In **`Python` we index from zero**, so the first element is `data[0, 0]`

```python
>>> print('first value in data:', data[0, 0])
first value in data: 0.0
>>> print('middle value in data:', data[30, 20])
middle value in data: 13.0
```

![progress check](images/red_green_sticky.png)

----

**SLIDE** Slicing arrays

- To get a section from the array, index using *square bracket* notation - but specify start and end points, separated by a colon
- The slice `0:4` means start at index zero and go up to, but not including, index 4. So it takes elements `0, 1, 2, 3` (four elements)

```python
>>> print(data[0:4, 0:10])
[[ 0.  0.  1.  3.  1.  2.  4.  7.  8.  3.]
 [ 0.  1.  2.  1.  2.  1.  3.  2.  2.  6.]
 [ 0.  1.  1.  3.  3.  2.  6.  2.  5.  9.]
 [ 0.  0.  2.  0.  4.  2.  2.  1.  6.  7.]]
>>> print(data[5:10, 0:10])
[[ 0.  0.  1.  2.  2.  4.  2.  1.  6.  4.]
 [ 0.  0.  2.  2.  4.  2.  2.  5.  5.  8.]
 [ 0.  0.  1.  2.  3.  1.  2.  3.  5.  3.]
 [ 0.  0.  0.  3.  1.  5.  6.  5.  5.  8.]
 [ 0.  1.  1.  2.  1.  3.  5.  3.  5.  8.]]
>>> print(data[2:4, 2:4])
[[ 1.  3.]
 [ 2.  0.]]
```

![progress check](images/red_green_sticky.png)

----

**SLIDE** More slices, please!

- If we don't specify a start for the slice, `Python` assumes the first element is meant (element zero)
- If we don't specify an end for the slice, `Python` assumes the last element is meant
- To get the top-right corner of the array, we can specify `data[:3, 36:]`

- **Explain `\n`**

```python
>>> small = data[:3, 36:]
>>> print('small is:\n', small)
small is:
 [[ 2.  3.  0.  0.]
 [ 1.  1.  0.  1.]
 [ 2.  2.  1.  1.]]
```

- **QUESTION: What does `:` on its own mean?**

```python
>>> print(data[0:2, :])
[[  0.   0.   1.   3.   1.   2.   4.   7.   8.   3.   3.   3.  10.   5.
    7.   4.   7.   7.  12.  18.   6.  13.  11.  11.   7.   7.   4.   6.
    8.   8.   4.   4.   5.   7.   3.   4.   2.   3.   0.   0.]
 [  0.   1.   2.   1.   2.   1.   3.   2.   2.   6.  10.  11.   5.   9.
    4.   4.   7.  16.   8.   6.  18.   4.  12.   5.  12.   7.  11.   5.
   11.   3.   3.   5.   4.   4.   5.   5.   1.   1.   0.   1.]]
```

----

**SLIDE** Exercise 03

**MCQ: put up four colours of sticky notes**

- The value is `oxyg`, number `1`

----

**SLIDE** Array operations


- Arithmetic operations on `array`s are **performed elementwise.**

```python
>>> doubledata = data * 2.0
```

- This operation multiplies every array element by 2.0.
- **Look at the top right corner of the original array**

```python
>>> print("original:\n", data[:3, 36:])
original:
 [[ 2.  3.  0.  0.]
 [ 1.  1.  0.  1.]
 [ 2.  2.  1.  1.]]
```

- **Look at the top right corner of the doubled array**

```python
>>> print("doubledata:\n", doubledata[:3, 36:])
doubledata:
 [[ 4.  6.  0.  0.]
 [ 2.  2.  0.  2.]
 [ 4.  4.  2.  2.]]
 >>> tripledata = doubledata + data
>>> print("tripledata:\n", tripledata[:3, 36:])
tripledata:
 [[ 6.  9.  0.  0.]
 [ 3.  3.  0.  3.]
 [ 6.  6.  3.  3.]]
```

----

**SLIDE** `numpy` functions

- `numpy` provides functions that can perform *more complex* operations on arrays
- Some of the **`numpy` operations include statistical summaries: `.mean()`, `.min()`, `.max()` etc.**

```python
>>> print(numpy.mean(data))
6.14875
```

- We can asssign the output from these functions to variables
- **By default, these functions give summaries of the whole array**

- **Introduce multiple assignment on one line, or use three lines**

```python
>>> maxval, minval, stdval = numpy.max(data), numpy.min(data), numpy.std(data)
>>> print('maximum inflammation:', maxval)
maximum inflammation: 20.0
>>> print('minimum inflammation:', minval)
minimum inflammation: 0.0
>>> print('standard deviation:', stdval)
standard deviation: 4.61383319712
```

- These functions can also be **applied directly to arrays**

```python
>>> maxval, minval, stdval = data.max(), data.min(), data.std()
>>> print('maximum inflammation:', maxval)
maximum inflammation: 20.0
>>> print('minimum inflammation:', minval)
minimum inflammation: 0.0
>>> print('standard deviation:', stdval)
standard deviation: 4.61383319712
```

![progress check](images/red_green_sticky.png)

----

**SLIDE** Summary for one patient

- **What if we want to get summaries patient-by-patient (row-by-row)?**
- We can extract a single row into a *temporary variable*, and calculate the mean for that variable

```python
>>> patient_0 = data[0, :] # temporary variable
>>> print('maximum inflammation for patient 0:', patient_0.max())
maximum inflammation for patient 0: 18.0
```

- **NOTE: that comments are preceded with a hash `#` and can be placed after a line of code**
- **EXPLAIN: why leaving comments is good (can do that in all code - not just Jupyter notebooks)**

- We can also **apply the `numpy` function directly**, without creating a variable

```python 
>>> print('maximum inflammation for patient 0:', numpy.max(data[0, :]))
maximum inflammation for patient 0: 18.0
>>> print('maximum inflammation for patient 2:', numpy.max(data[2, :]))
maximum inflammation for patient 2: 19.0
```

---- 

**SLIDE** Summary for all patients

- But **what if we want to know about all patients at once?**
- Or **what if we want an average inflammation per day?**

- Writing one line per row, or per column, is likely to lead to mistakes and typos
  - **We can specify which axis a function applies to**

- Specifying `axis=0` makes the function work on columns (days)
  - **working on values 'by' row/row-wise**
- Specifying `axis=1` makes the function work on rows (patients)
  - **working on values 'by' column/column-wise**

----

**SLIDE** `numpy` operations on axes

- **`numpy` functions take an `axis=` parameter** which controls the axis for summary statistic calculations.

```python
>>> print(numpy.max(data, axis=1))
[ 18.  18.  19.  17.  17.  18.  17.  20.  17.  18.  18.  18.  17.  16.  17.
  18.  19.  19.  17.  19.  19.  16.  17.  15.  17.  17.  18.  17.  20.  17.
  16.  19.  15.  15.  19.  17.  16.  17.  19.  16.  18.  19.  16.  19.  18.
  16.  19.  15.  16.  18.  14.  20.  17.  15.  17.  16.  17.  19.  18.  18.]
>>> print(data.mean(axis=0))
[  0.           0.45         1.11666667   1.75         2.43333333   3.15
   3.8          3.88333333   5.23333333   5.51666667   5.95         5.9
   8.35         7.73333333   8.36666667   9.5          9.58333333
  10.63333333  11.56666667  12.35        13.25        11.96666667
  11.03333333  10.16666667  10.           8.66666667   9.15         7.25
   7.33333333   6.58333333   6.06666667   5.95         5.11666667   3.6
   3.3          3.56666667   2.48333333   1.5          1.13333333
   0.56666667]
   ```

![progress check](images/red_green_sticky.png)

----

## SECTION 04: Visualisation

----

**SLIDE** Visualisation

> "The purpose of computing is insight, not numbers" - Richard Hamming

- The best way to gain insight is often to visualise data.
- Visualisation is a large topic that deserves more attention
  - **We're just scratching the surface, here**

----

**SLIDE** Graphics package `matplotlib`

- `matplotlib` is the *de facto* standard/base plotting library in `Python`

```python
>>> import matplotlib.pyplot
```

- We use `matplotlib.pyplot` to make the interaction a bit more like `matlab`

![progress check](images/red_green_sticky.png)

----

**SLIDE** `matplotlib.pyplot.imshow()` 

- The `.imshow()` function **converts matrix values into an image**

```python
>>> image = matplotlib.pyplot.imshow(data)
>>> matplotlib.pyplot.show()
```

- Here, small values are blue, and large values are yellow (**you can change this colour scheme with other settings…**)
- From the image, we can see **inflammation rising and falling** over a 40-day period for all patients.

- **QUESTION: does this look reasonable?**

----

**SLIDE** `matplotlib.pyplot.plot()`

- **`.plot()` shows a conventional line graph**
- We're going to use it to **plot the average inflammation level on each day of the study**
- We'll create the variable `ave_inflammation` and use `numpy.mean()` on axis `0` of the data

```python
>>> ave_inflammation = numpy.mean(data, axis=0)
>>> ave_plot = matplotlib.pyplot.plot(ave_inflammation)
>>> matplotlib.pyplot.show()
```

- **NOTE: ask students if the data looks reasonable?**
  - The **data does not look reasonable**. Biologically, we expect a sharp rise in inflammation, followed by a slow tail-off

----

**SLIDE** Investigating data

- Since **our plot of `.mean()` values looks artificial, let's check on other statistics** to see if we can see what's going on.
- We'll plot the maximum value by day

```python
>>> max_plot = matplotlib.pyplot.plot(numpy.max(data, axis=0))
>>> matplotlib.pyplot.show()
```

- **NOTE we're not defining a variable, this time**

```python
>>> min_plot = matplotlib.pyplot.plot(numpy.min(data, axis=0))
>>> matplotlib.pyplot.show()
```

- **Ask students if the data looks reasonable?**
  - The data looks very artificial. The maxima are completely smooth, but the minima are a 
step function.

- **NOTE: we would not have noticed this without visualisation**

----

**SLIDE** Exercise 04 (5min)

```python
>>> std_plot = matplotlib.pyplot.plot(numpy.std(data, axis=0))
>>> matplotlib.pyplot.show()
```

![progress check](images/red_green_sticky.png)

----
**SLIDE** FIGURES AND SUBPLOTS

**WE'RE WORKING IN A SCRIPT FOR THE FIRST TIME**

- **Exit `Python`**
- **Open a new script called `subplots.py`**

```bash
$ nano subplots.py
```

- **You're now in the `nano` editor**
- We write the `Python` code here, then save it, exit, and run it with `python subplots.py`.

- **DESCRIBE SCRIPT**
- First we **import packages**

```python
import numpy
import matplotlib.pyplot
```

- Next we **load data**
  - Comments tell us why/what we are doing

```python
# Load inflammation data
data = numpy.loadtxt(fname='data/inflammation-01.csv', delimiter=',')
```

- We can put all three plots we just drew into a single figure
- To do this, we use `matplotlib` to **create a figure**, and put it in a variable called `fig`
  - the `figsize` argument sets the `(width, height)` of the figure in inches

```python
# Create a figure
fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0))
```

- We then **create three *axes***
  - these are the variables that hold the individual plots
  - one axis per plot
- Using the `.add_subplot()` function, we need to specify three things:
-* number of rows, number of columns, which cell this figure goes into
  - **THIS NEEDS TO BE DRAWN OUT ON THE BOARD**

```python
# Add subplots for statistical summaries
axes1 = fig.add_subplot(1, 3, 1) 
axes2 = fig.add_subplot(1, 3, 2)
axes3 = fig.add_subplot(1, 3, 3)
```

- Once we've created our plot axes, we can add labels and plots to each of them in turn
- Plot axes properties are usually changed using the `.set_<something>()` syntax
  - Here we're changing only the label on the *y*-axis

```python
# Add y-axis label to each subplot
axes1.set_ylabel('average')
axes2.set_ylabel('max')
axes3.set_ylabel('min')
```
  
- We can plot on an axis by using its `.plot()` function
  - As before, we can pass the output from the `numpy.max()` function directly

```python
# Plot the summary data
axes1.plot(numpy.mean(data, axis=0))
axes2.plot(numpy.max(data, axis=0))
axes3.plot(numpy.min(data, axis=0))
```

- We'll tighten up the presentation by using `fig.tight_layout()`
  - this is a function that moves the axes until they are visually pleasing.

```python
# Tidy the figure
fig.tight_layout()
```

- Finally, we'll show the figure in the interactive window

```python
# Show figure in the interactive window
matplotlib.pyplot.show()
```

- **Write the file**
- **Save the file**
- **Exit to terminal**

- Now we run the script with `python subplots.py`

```bash
$ python subplots.py
```

* **This is the most demanding code you have written, so far! ROUND OF APPLAUSE FOR YOURSELVES!**

----

**SLIDE** Exercise 05 (5min)


- Note that it helps to change `figsize`
- Otherwise the only change is in `add_subplot()`

- `cp` the file to prepare for a new script

```bash
$ cp subplots.py exercise_05.py
$ nano exercise_05.py
```

- New script:

```python
import numpy
import matplotlib.pyplot

# Load inflammation data
data = numpy.loadtxt(fname='data/inflammation-01.csv', delimiter=',')

# Create a figure
fig = matplotlib.pyplot.figure(figsize=(3.0, 10.0))

# Add subplots for statistical summaries
axes1 = fig.add_subplot(3, 1, 1)
axes2 = fig.add_subplot(3, 1, 2)
axes3 = fig.add_subplot(3, 1, 3)

# Add y-axis label to each subplot
axes1.set_ylabel('average')
axes2.set_ylabel('max')
axes3.set_ylabel('min')

# Plot the summary data
axes1.plot(numpy.mean(data, axis=0))
axes2.plot(numpy.max(data, axis=0))
axes3.plot(numpy.min(data, axis=0))

# Tidy the figure
fig.tight_layout()

# Show figure in the interactive window
matplotlib.pyplot.show()
```

- Execute script

```bash
$ python subplots.py
```

![progress check](images/red_green_sticky.png)

* **NOW, TO DO *EVEN MORE* INTERESTING THINGS, WE NEED TO LEARN A LITTLE MORE ABOUT PROGRAMMING**
