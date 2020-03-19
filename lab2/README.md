# Synpsis
The goal of this exercise is to get familiar with the project structure and make the minimum changes so that you can hava a successful build on the `master` branch.

# Clean
1. You first need to have clean repository, i.e. no changes. You have to commit everything you have worked on:
```
git add .
git commit -m "describe your changes"
```

2. Make sure you are on the master: `git checkout master`

# Prepare
1. Get the code. To get updates from github, you just need to run `git pull`. You should now see lab2 folder. 
2. Go to the folder (in the terminal, `cd lab2`)
3. Prepare the build:
  * For Linux/Mac, run: `cmake .`
  * For Windows, run: `cmake . -G "MinGW Makefiles"`

# Project structure
The project is split into several classes organized in several files. The `main.cpp` is the entry point of the program. __You should not make any changes to the `main.cpp`.__

## Classes
Each class is split into two files:
* `something.h`  - the header files (i.e. `*.h`) contains the declaration of the class, its member functions and variables. It is `included` via the `#include` directive in other `.cpp` files.
* `something.cpp` - the CPP file contains the definition of the class member functions. It is what is actually compiled

There are 4 classes in the program:
* `Invoice` - responsible for the state of the invoice being prepared, i.e. the products, quantities, totals, etc. It uses the `Item` class to keep track of product quantities. and is used by the `TextPrinter` class.
* `Item` - responsible for tracking quantity and a subtotal of a given product, i.e. a line item of an invoice. It uses the `Product` class and is used by the `Invoice` class.
* `Product` - responsible for the information about the product, i.e. name and price.
* `TextPrinter` - responsible for printing invoice information to an output stream (e.g. `cout`). It uses the `Invoice` member functions to extract and present the information.

The `main.cpp` gives you the frame. In order to make it work and compile, you will need to make several changes to the class files. 

# Exercise

You should work in small iterations towards completing the exercise. I will illustrate the steps with a few examples, and then you should try on your own until you get to the final result.

The steps that we will be repeating are the following:
1. Build the program with `make` on Mac/Linux or `mingw32-make` on Windows.
2. Look at the first error.
3. Fix the first error so it dissapears (i.e. the code compiles, changes only in the `.h` files)
4. Go to #1 until no more errors during compilation.
5. Build the program with `make` on Mac/Linux or `mingw32-make` on Windows.
7. Linking fails - look at the first error and fix it by making changes in the `.cpp` files. Define empty member functions - don't try to implement them, our goal is to produce an executable.

Basically, when you repeat the process above several times, you will have an executable file `lab1.exe` on Windows or `lab` on Linux/Mac that doesn't do anything. 
