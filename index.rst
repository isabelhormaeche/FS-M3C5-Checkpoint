********************************************************
M3C5 - Checkpoint - Python Documentation Assignment
********************************************************

1. What is a conditional?
=================================
Conditionals are very useful control structures in Python that allow us to make decisions based on the value of an expression. In other words, conditionals allow us to make Python take different paths depending on whether a certain condition is met or not (True or False).

Conditionals are essential for creating dynamic behavior in Python programs. They allow us to control the flow of execution based on specific conditions, making our code more flexible and responsive. (IT)

Conditional statements in Python are primarily constructed by using the ``if``, ``elif``, and ``else`` keywords:

1.1. The ``if`` Statement
---------------------------

The ``if`` statement allows you to execute a block of code if a certain condition is true. Here's the basic syntax: ::
   
   if condition:
       # code to execute if condition is true


.. admonition:: Remember 

    Keep in mind that proper indentation (usually 2 or 4 spaces) is crucial when using conditional statements in Python. The level of indentation determines which code block is executed based on the condition. The condition can be any expression that evaluates to a Boolean value (True or False). If the condition is True, the indented code block below the ``if`` statement will be executed; otherwise, it will be skipped.

Here's an example of how to use an ``if`` statement:::

    a = 1
    b = 2

    if b > a:
        print(" b is in fact bigger than a") #Output: b is in fact bigger than a

In this example, we use the ```>``` operator to compare the value of a to b. If b is greater than a (True) the code block indented below the if statement will be executed, and the message " b is in fact bigger than a” will be printed. If it wasn't (True), nothing would have happened. No code would have run.

1.2. The ``if-else`` Statement 
------------------------------

The ``if-else`` structure allows us to execute one statement if the condition is met (True), and another statement if the condition is not met (False). The ``else`` statement allows you to execute a different block of code if the ``if`` condition is False. Here's the basic syntax::

    if condition:
        # code to execute if condition is true
    else:
        # code to execute if condition is false


If the condition is True, the code block indented below the ``if`` statement will be executed, and the code block indented below the else statement will be skipped.

If the condition is False, the code block indented below the ``else`` statement will be executed, and the code block indented below the ``if`` statement will be skipped.


Here's an example of how to use an ``if-else`` statement::


    if age < 25:
         print(f"I'm sorry, you need to be at least 25 years old  to rent a car")
     else:
         print(f"You're good to go, {age} fits in the range to rent a car.")
    #condition is either True or False

1.3. ``if-elif-else`` Statement 
-----------------------------------
The ``elif`` statement is short for ``else if``. It allows you to check multiple conditions in sequence and execute different code blocks depending on which condition is true. Here's the basic syntax::

    if condition1:
        # code to execute if condition1 is true
    elif condition2:
        # code to execute if condition1 is false and condition2 is true
    elif condition3:
        # code to execute if condition1 and condition2 are false, and condition3 is true
    else:
        # code to execute if all conditions are false

Here's an example of how to use an ``if-elif-else`` statement::

    if age < 25:
        print(f"I'm sorry, you need to be at least 25 years old")
    elif age > 100:
        print(f"I'm sorry, {age} is too old to rent a car")
    else:
        print(f"You're good to go, {age} fits in the range to rent a car.")


If the two first conditions ``if`` and ``else`` are false it goes to check the final statement ``else`` and it is going to run whatever is inside of that final code block.
When checking multiple conditions, consider using elif to avoid excessive nesting.

1.4. The Ternary Operator in Python Conditionals
-----------------------------------------------------
The Ternary Operator allows you to create an ``if-else`` statement on a single line.

.. Note::`Simple is better than complex` referencing PEP 20 which is the Zen of Python. When implementing the ternary operator, you need to make sure that is better than simply going with a standard ``if-else`` statement. Because ``if`` you make your code harder to read and will be more challenging for you (when you go back and look at the code in the future) and for other developers that you are working with.

For example: you are building out some kind of web application that needs to have an authorization component. If role is set to admin (administrator)then we want them to access the dashboard. And if not (a guest user) then cannot access.

We assign whatever the result of the ternary operator inside the variable auth::

    #role = 'admin'
    role = 'guest'
    auth = 'can access' if role == 'admin' else 'cannot access'
    print(auth)
   
If it meets the ``if`` condition, auth it will save the value "can access", otherwise, it will save the value “cannot access” of the ``else``.

1.5. Full List of Python Conditional Operators
---------------------------------------------------------
Conditional Operators are what we place inside of our condition to check for elements such as equality or inequality. We also can test for value ranges such as checking to see if an element is greater than or equal to a value or if it is lesser than or equal to another value. Python supports the usual logical conditions from mathematics:

List of comparison operators:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

* == Equality
* != Inequality
* <> Inequality (deprecated) 
* >  Greater than
* >= Greater than or equal to
* <  Less than
* <= Less than or equal to
  


We can implement them with various data structures such as `numbers`, `strings` and lists  tuples and dictionaries.

Here are some examples of Equality and Inequality operators working for both NUMBERS and STRINGS.

Equality with `numbers`:
~~~~~~~~~~~~~~~~~~~~~~~~~~
Example::

    age = 55

    if age != 90:
        print("Welcome!")
    else:
        print("You shall not pass!")


Equality with a `strings`:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Example::

    username = "jonsnow"
    #username = "Alex"

    if username == "jonsnow":
        print("Welcome!")
    else:
        print("You shall not pass!")

.. Note::El <<==>> es un operador de comparación (compara si es exactamente igual) es importante recordar que hay que utilizar un doble signo igual. Si utilizas sólo <<=>> en el ``if``, estarás utilizando el operador de asignación, es decir estableciendo que username es igual a jonsnow con lo que la condición siempre sería cierta 

Example of equality implement with a `list`:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Some real cases when we may want to compare two identical lists could be for example:

* when we are building out a system that checks for duplicates or
* if we are implementing a machine learning algorithm and you're checking to see if your historical data is matching up with some of the current test data that you're working with.

    user_list = ["kristine", "Tiffany"]
    second_list = ["kristine", "Tiffany"]

    if user_list == second_list:
        print("They match")


We also have a full set of greater than and less than operators. But, **these only work for numbers**:

* >  Greater than
* >= Greater than or equal to
* <= Less than
* <= Less than or equal to
  
For example::

    age = 55
    if age > 10:
        print("Welcome!")
    else:
        print("You shall not pass!")
   
1.6. ``in`` operator
----------------------

We can also use the ``in`` operator to check to see if one element is inside or contained in another element in a Python String or List. 

1.6.1. In a string
~~~~~~~~~~~~~~~~~~~~~~~
As in this example::

    sentence = 'The quick brown fox jumped over the lazy Dog'
    #word = 'quick'
    word = "dog"             # ***ATTENTION!!!!*** is CASE SENSITIVE
    
    if word in sentence:
        print("The word was found in the sentence")
    else:
        print("The word was not found in the sentence")



**To make it case insensitive we add the lower() function**.

For example::
    
    if word.lower() in sentence.lower():
        print("The word was found in the sentence")
    else:
        print("The word was not found in the sentence")



1.6.2. In a list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``in`` can also work with `collections of data` such as ``lists``

As in this example::

    nums = [1, 2, 3, 4]
    if 3 in nums:
        print("The number was found")
    else:
        print("The number was not found")


1.7. Compound Conditionals
-------------------------------

Another type of conditional in Python are the compound conditionals that allow us to add multiple conditions inside in the same statement. When we need to use more than one condition we can use the `and` and ``or`` operators. 

1.7.1. ``add`` operator
~~~~~~~~~~~~~~~~~~~~~~~~~
We can build what is called the ``and`` operator into our system when we want to check if two conditions are true at the same time.

Everything on the left-hand side of the and the right-hand side must be true in order for the code block to be executed.

It is very useful when we want to add a higher level of difficulty or a high-level of restriction because we are chaining on multiple conditions that have to be true in order to work::

    username = 'jonsnow'
    username = 'sansa'
    email = 'jon@snow.com'
    password = 'thenorth'

    if username == "jonsnow" and password == "thenorth":
       print("Acess permitted")
    else:
       print("You shall not pass!")

1.7.2. ``or`` operator
~~~~~~~~~~~~~~~~~~~~~~~
In the case of the ``or`` operator it means "or" and we will use it when we only need one of the conditions to be met. So, it is a little bit more flexible compared with using and operator.

Example of ``or``::
   
    if username == "jonsnow" or password == "thenorth":
         print("Acess permitted")
    else:
        print("You shall not pass!") ## returns true--> access permit EVEN  if I put username = "sansa"
  
    #The way the `or` operator works is it looks at the full expression it first checks to see on the left-hand side. If it's true it just skips everything to the right because all that has to occur for the or operation to be considered true is for one side to match up and for one to be true.

1.7.3. Nested ``if``
~~~~~~~~~~~~~~~~~~~~~
The conditions are placed inside of each other and will work exactly the same way. But, it is not recommended this way::

   
     if username == "jonsnow":
         if password == "thenorth":
           print("Acess permit")
     else:
         print("You shall not pass!")
   

References and further reading
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can consult more information about the **conditionals** on the following links:

https://apuntes.de/python/estructuras-de-control-condicionales-y-bucles-en-python/#gsc.tab=0
https://www.freecodecamp.org/news/python-if-else-statement-conditional-statements-explained/
https://cosasdedevs.com/posts/sentencias-if-elif-else-python/
https://docs.python.org/3/reference/compound_stmts.html#the-if-statement
https://python-textbok.readthedocs.io/en/1.0/Python_Basics.html

Exercises for practice:
~~~~~~~~~~~~~~~~~~~~~~~~

https://www.w3schools.com/python/exercise.asp?filename=exercise_ifelse1

2. What are the different types of loops in python? Why are they useful?
========================================================================
Loops are helpful when you want to automate a specific repetitive task or prevent yourself from copying and pasting the same code in your program.

Loops in computer programming repeat the same block of code or the same sequence of instructions multiple times until a condition is met or until a condition is no longer met.

Using loops in our program will help us save time, minimize errors, and stop repeating ourselves.

There are two types of loops in Python: `for` loops  and `while` loops.

2.1. `for` Loop
----------------
The `for` loop iterates over each item in the sequence (that is either a list, a tuple, a dictionary, a set, or a string) in order. And it executes the same block of code for every item. Because of this behavior, the `for` loop is helpful when:

* You know the number of times you want to execute a block of code.

* You want to execute the same code for each item in a given sequence.

The general syntax for a for loop in Python looks like this: ::

    for placeholder_variable in sequence:
    # code that does something




Example: Print each fruit in a fruit list: ::

    fruits = ["apple", "banana", "cherry"]

    for x in fruits:
    print(x)

2.1.1. How to Implement Python Loops for Lists, Tuples, and Dictionaries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Looping Through a List
~~~~~~~~~~~~~~~~~~~~~~~~~

Example::


    nombre = 'Enrique'
    lista_nombre = ['Jessica', 'Paul', 'George', 'Henry', 'Adán']

    for nombre_lista in lista_nombre:

        if nombre_lista == nombre:
            print(f"{nombre} aparece en la lista")
            break
        else:
            print(f"{nombre} no aparece en la lista")


Looping Through a String
~~~~~~~~~~~~~~~~~~~~~~~~~~~
We could treat a string like a collection of characters and iterate through that collection, like a list::
    
    name = "Isabel"

    for letter in name:
        print(letter)
    # output

    # I
    # s
    # a
    # b
    # e
    # l


Looping Through a Dictionary
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
To loop over key and value pairs in a dictionary, we need to do what is called tuple unpacking by specifying two variables.

We will also need to use the .items() method to loop over both the keys and values.::

    interviewed_info = {
    'name':'Nadal',
    'job title':'tennis player',
    'country':'Spain'
    }

    for key,value in interviewed_info.items():
    print(key,":",value)
    #output
    #name : Nadal
    #job title : tennis player
    #country : Spain

Looping Over Ranges
~~~~~~~~~~~~~~~~~~~
We have the kind of control and flexibility for only grabbing the elements and the intervals that we actually  want to show.

It is practical tool when we know that we have a set number of times that we want to loop through some specific data set but we do not want to limit it to how many items are in some type of collection such as iterating over a list.

The way that a range works is very similar to grabbing items and slicing items inside of a list. Python treats the second argument as an upper bound which means it do not actually go up to 10. 
For example if we want 10, we will do::
    
    for num in range(1, 11):
        print(num) #Output: 1 2 3 4 5 6 7 8 9 10 # iterates through 1 to 10!!! just before 11.


When we want to skip values in our loop. To achieve this, we set the step to 2::
    
    for num in range(1, 11, 2):
        print(num)  # Output: 1 2 5 7 9

Instead of the default behavior where the loop increments by 1 in each iteration, this modified loop skips every second value, resulting in the output shown above.

2.1.2.Control flow logic operators: **Continue** and **Break** in Loops
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
By default, a for loop in Python will loop through the entire iterable object until it reaches the end.
However, there may be times when we want to stop or alter the behavior somewhere in the middle of the loop based on a condition. 

We have two different types of control flow logic operators: `continue` and `Break`. 

Continue
~~~~~~~~~~~~~
The `continue` statement stops the current iteration at a specific point and moves on to the next item of the iterable object. It does not exit the loop entirely. Check the following example::

    usernames = [
    'jon',
    'tyrion',
    'theon',
    'cersei',
    'sansa',
    ]

    for username in usernames:
        if username == 'cersei':
            print(f'Sorry, {username}, you are not allowed') #(format statement)
            continue
        else:
            print(f"{username} is allowed")  
    #OUTPUT 
            #jon is allowed
            # tyrion is allowed
            # theon is allowed
            # Sorry, cersei, you are not allowed
            # sansa is allowed

Break
~~~~~~~~~~~~~
We can use the `break` statement when we may want to exit the loop prematurely if a specific condition is met.
In the following example below, we simply want to search (“cersei”) and then once we have found what we were looking for then, we want the program to stop and exit the loop::

    for username in usernames:
        if username == 'cersei':
            print(f"{username} was found at index {usernames.index(username)}")
            break
        print(username)  # returns: 
        # jon
        # tyrion
        # theon
        # cersei was found at index 3

`break` stops the loop and it stops at the first element (“cersei”) that matches the condition. And exit the loop.


2.2. While loop
------------------

Essentially, a `while True` loop is a loop that is continuously `True` and therefore runs endlessly. It will never stop until we force it to stop.

The key difference between using a `for-in` loop vs a `while` loop. With a `for-in` loop we have a very clearly defined start and finish to our loop. With a `while` loop you do not have a definite start and finish.

The general syntax for writing a `While` loop in Python looks like this::

    while condition:
        body of while loop containing code that does something


`While` Loop will not stop when it reaches the end of a list (if that's what we are iterating over) has to explicitly be told when to stop. 
We have to set a sentinel value in order to tell our while loop when to stop.

2.2.1. When we know when we want to stop:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Here we have an example, where the sentinel value is when the length of our number list was not greater than 0.::

    nums = list(range(1, 100))

    while len(nums) > 0:    # sentinel value 
        print(nums.pop())
        #itirate over our list it will pop off the last element of the list and print it out and remove it form the list. It starts form the end, with 99 and then 98 and then 97 and so on.

2.2.2. When we do not know when we want to stop: 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Here we have an example of a while true loop. 
  
  It is a guess-number game with a while True loop. This means the loop will continue indefinitely until a specific condition is met. We use a sentinel value (guess == "42") and  where whenever the correct guess is presented by the user, it will execute the instruction “return false” and that will stop our while loop::
    
        while True:
            print("What is your guess?") # Prompt the user for input
            guess = input()

            if guess == "42":
                print("You correctly guessed it!")
                return False   
            else:
                print(f"No, {guess} is not the answer, please try again\n") # Prompt the user for input again

  Within the above loop, this is what happens:

  * It prints the message “What is your guess?” to prompt the user for input.
  * It reads the user’s input and assigns it to the variable guess.
  * If the user’s input is equal to the string “42”, it prints “You correctly guessed it!” and returns False, effectively ending the loop.
  * Otherwise, it prints a message indicating that the guess is incorrect and prompts the user to try again.

2.3. Summarizing 
-------------------------
It is important that we make sure the `for` or  `while` loop has a termination condition to avoid infinite loops.
The main **differences** between for loops and while loops in Python are:

* **for** Loop:

  It is used when the number of iterations is predetermined. It’s commonly used for iterating over sequences like lists, tuples, strings, or ranges.
  The loop iterates over each item in the sequence and executes a block of statements for 
  each item.

  Efficient for sequences with a predetermined length.

* **while** Loop:

  A while loop operates without prior knowledge of the number of iterations(e.g., waiting for user input). It continues to execute a block of statements while a condition remains true. 

**References and further reading**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can consult more information about the ***Loops*** on the following links:
https://www.freecodecamp.org/news/for-loops-in-python-with-example-code/
https://www.w3schools.com/python/python_for_loops.asp


**Exercises for practice:**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://www.w3schools.com/python/python_for_loops.asp
Loops - Learn Python - Free Interactive Python Tutorial 


3. What is List Comprehension in Python?
=================================================

It is a very powerful tool in Python that allows us to create new lists out of existing lists.

We can use it to filter, format, modify, or do other small tasks on existing iterables.

List comprehension is essentially a set of for-in loops and conditionals that can all be placed  inside of ***a single line of code*** enclosed in square brackets. 

It is a good choice if we want to keep our code compact and readable.

For example, bellow we create a list that catches even numbers::

    num_list = range(1, 11)
    even_numbers = []
    for num in num_list:
        if num % 2 == 0:        
        even_numbers.append(num)

    print(even_numbers) # [2, 4, 6, 8, 10]

We now use list comprehension and we see our code looks simple, compact, and faster.::

    even_numbers = [num for num in num_list if num % 2 == 0]
    print(even_numbers) # [2, 4, 6, 8, 10]

Above we saw how list comprehension was able to complete a task in just a single line which a for loop completed in multiple lines. But we should avoid using list comprehension if you have too many conditions to add for filtering or modifying as it will make your code more complex and harder to read.

Additionally, when we work with massive sets of information, lists can present us with an efficiency and memory limitation problem.

What happens when we need to create, for example, a list of 1 million numbers? Creating such a large list would not be very practical and would probably consume all the available memory on the computer. In this situation, generators are a perfect solution.

To learn  about **generators** and see some examples we can check this link: https://apuntes.de/python/generadores-y-comprensiones-de-listas-en-python-eficiencia-y-flexibilidad/#gsc.tab=0 

**References and further reading**

You can find some more information about the *** List Comprehension in Python *** on the following links:
https://docs.python.org/dev/tutorial/datastructures.html#list-comprehensions
https://apuntes.de/python/generadores-y-comprensiones-de-listas-en-python-eficiencia-y-flexibilidad/#gsc.tab=0 

**Exercises for practice:**

List Comprehensions - Learn Python - Free Interactive Python Tutorial https://www.learnpython.org/en/List_Comprehensions


4. What is an argument in Python?
=================================================
Arguments in functions refer to values that are passed to a function to perform a specific task. Information can be passed into functions as arguments.
There are different types of arguments that can be passed to a function in Python:

4.1.Default arguments
------------------------------------

Default arguments are values that are assigned to the parameters of a function in case values are not supplied for them when calling the function. This can be useful to provide a default value that the function can use if a specific value is not provided.

    def greeting(name = 'Guest'):
    #   print(f'Hi {name}!')

    # greeting()		#Hi Guest!
    # greeting('Isabel')     # Hi Isabel! 

But whenever we do pass in a string (Example above: Isabel) then that overrides the default argument.

4.2.Positional arguments
------------------------------------

These types of arguments are passed to a function in the order in which they were defined in the function (the order that we passed the values in while creating the function). For example:::

    def sum(a, b):
        return a + b

    result = sum(2, 3)
    print(result) # Print 5

In this example, the arguments a and b are positional arguments and are passed in the order in which they were defined in the signature of the sum function.

But when it comes to working with larger programs and more advanced functionality having positional arguments can lead to some confusion.

Named arguments give you the ability to be much more explicit with the mapping.

4.3. Named arguments
------------------------------------

Named arguments are passed to a function by specifying their name in the function call. 

Named arguments explicitly declared the mapping then, they allow us to pass in whatever our values are in whatever order we prefer. 

These types of arguments provide greater clarity and readability to the code.::

    def full_name(first, last):
    print(f'{first} {last}')

    full_name(first = “Rafael”, last = “Nadal”) #Rafael Nadal
    full_name(last = '“Nadal”, first = “Rafael”) #Rafael Nadal

.. Notes: It is considered a very bad practice to ever set a default argument as a list.

All functions can use either named or pure positional arguments and it's completely up to us. But, if there are more than 2 arguments, it is recommended to use named arguments simply because it prevents any issues with us placing the values in the wrong order or calling the wrong name or anything related to that.

4.4. Unpacking arguments/Arbitrary arguments
--------------------------------------------------
There are many times where we have a function that needs to take in a collection of data. So we may not know if we are going to have one element or if we are going to have 50 elements and we cannot simply place a hard-coded list of items. 

Function unpacking arguments are a very useful tool in Python, allowing us to work with an indeterminate number of elements in a function. 

Arguments with ``*`` are used to work with lists and tuples, while arguments with ``**`` are used to work with dictionaries and to define named arguments in a function. 

With its use, we manage to give greater flexibility and adaptability to our functions, which is essential in programming.

The syntax for using unpacking is: We start off with a star  ``*`` and then the common convention is to name the argument list  ``args``. This represents an unpacked version or a list of items that are going to be passed into the function.
Use of ``*args``::

    def today_menu(*args):
        print("Today´s menu:")
        for arg in args:
            print(f'* {arg}')

    today_menu('Soup', 'Teriyaki Chicken', 'Cheesecake', 'One drink')
    #output 
    Today´s menu:
    * Soup
    * Teriyaki Chicken
    * Cheesecake
    * One drink
  

Use of Keyword Arguments `*kargs`:

Python does have a way where we can take in a keyword list of arguments. Example: ::

    def greeting(**kwargs):
        if kwargs:
            print(f"Hi {kwargs['first_name']} {kwargs['last_name']}, have a great day!")
        else:
            print('Hi Guest have a great day!')

    greeting()     #Hi Guest have a great day!
    greeting(first_name = "Rafa", last_name = "Nadal")      #Hi Rafa Nadal, have a great day!

4.5. How to Combine `all argument types` in a Single Python Function Unpacking arguments
---------------------------------------------------------------------------------------------

Example: ::

    def greeting(time_of_day, *args, **kwargs):
            print(f"Hi {' '.join(args)}, I hope that you're having a good {time_of_day}.")
            if kwargs:
                print('Today´s menu at the Pool Bar is:')

                for key, val in kwargs.items():
                print(f'{key} - {val}')

    greeting('Morning',
                    'Rafa', 'Nadal',
                    Starter = ' Miso Soup',
                    Main = 'Teriyaki Chicken',
                    Dessert = 'Cheesecake',
                    Drink = 'One drink')

    # Output:  a greeting with a full set of arguments.::

        #Hi Rafa Nadal, I hope that you're having a good Morning.
        #Today´s menu at the Pool Bar is:
        #Starter - Miso Soup
        #Main - Teriyaki Chicken
        #Dessert - Cheesecake
        #Drink - One drink

Process: 

We have started with a positional argument then we passed in a set of items or which is going to be converted into a tuple of arguments and then we passed in a full set of keyword argument.  
And `.join` takes in a collection and then, it converts it and outputs a string.

References and further reading:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
You can consult more information about the ***Arguments*** on the following links:
https://apuntes.de/python/manejo-de-argumentos-en-funciones-python-flexibilidad-y-adaptabilidad/#gsc.tab=0

Exercises for practice:
~~~~~~~~~~~~~~~~~~~~~~~~
Exercises: https://www.w3schools.com/python/python_functions.asp 


5. What is a Python Lambda function?
=================================================

The lambda function gives you the ability to wrap functionality, store it in a variable and then pass that entire process to other functions and other parts of your program quickly and easily.

A lambda function is a small anonymous function. It allows you to write a function on a single line. Usually, a smaller function and that can be easily pass it as an argument to other functions.


It is a tool that allows you to wrap up a process, a function and returns a value so we are pretty much always going to be using a lambda where we are returning something.

.. Note::a lambda is only going to return the value. No print.


To create a lambda, we just say Lambda, followed by the list of arguments (first, last).  The syntax of the lambda expression in python is as follows::

    lambda arguments: expression

Example:

Whatever comes after the colon is going to be the value that is returned(formatted string).::

    full_name = lambda first, last: f'{first} {last}'
    print(full_name("Rafael", "Nadal"))

We return a full_name value and will be stored in the variable full_name.


Now, we use the lambda full_name as an argument inside the greeting function.::

    def greeting(name):
        print(f"Hi there {name}")

    greeting(full_name("Rafael", "Nadal"))




You can have some more information about the **Lambda function** on the following link:
https://www.freecodecamp.org/espanol/news/expresiones-lambda-en-python/
And you can practice some exercises here: https://www.w3schools.com/python/python_lambda.asp 





6. What is a pip package?
=================================================
Pip is a recursive acronym that stands for either pip installs packages or pip installs python.

Pip is the package management system used to install and manage external libraries in Python (that do not come with the default Python installation). With Pip, it is easy to install and update packages. The management system makes sure that all dependencies are installed correctly and always keeps everything up to date.::

    pip install package_name

Pip allows you to call outside packages that are stored inside of what is called the Pypi store or the Cheese shop (https://pypi.org/ ). We can bring in modules and packages (code) that other developers have created, and we can use those in our own programs.

In order to use it, you first have to install it on your system.

6.1. How to Install PIP On a Mac or Windows Machine
--------------------------------------------------------------------

Usually, pip is automatically installed if you are: working in a virtual environment or using Python downloaded from python.org.
To make sure it is installed, simply open a terminal window and run simply type in: ::

    pip –version

and if it is installed on your system then it will show the version and the location where pip is stored.

However, if your Python environment does not have `pip` already installed then you can download it from this page: https://pip.pypa.io/en/stable/installation/  and download this file `get-pip.py` and you have to open up the terminal and run it like a regular python file.::
Python get-pip.py
Then hit return and it will install the entire pip library on your system.

..Note: Keep pip updated to have access to the latest package versions and security improvements.

Once pip is installed we can bring some popular packages into our program. 

The Python Package Index (PyPI) is a software repository for the Python programming language that help you find and install programs developed and shared by the Python community. You can use its search engine to look for packages. https://pypi.org/

6.2. PIP´s Syntax
----------------------

Pip's syntax is very simple:

* To see a list of all packages installed in your environment along with their versions, use this command:::

    pip list

* To install a package, use the this command:::
  
    pip install package_name

* To remove a package that you no longer use, you can do so with the following command:

    pip unstall package_name

Some more information related to pip commands can be found here: https://pip.pypa.io/en/stable/cli/

6.3. Example: Using Pip for importing NumPy library
-----------------------------------------------------------------------

We are going to import the NumPy library and use it to create an entire matrix of values using NumPy.

NumPy  is a very powerful package that allows you to process numbers, records, and objects. It allows you to process large collections of data in a very efficient manner. So usually, things that would take you many lines of code to write, numPy has those processes built directly in the library and you can simply call them and then use them in your own programs.

    import numpy as np

    num_range = np.arange(16)

    num_range

    # array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15])

    num_range.reshape(4, 4)

    # array([[ 0,  1,  2,  3],
        [ 4,  5,  6,  7],
        [ 8,  9, 10, 11],
        [12, 13, 14, 15]])

Process explained:
~~~~~~~~~~~~~~~~~~~~

We import the NumPy library. This allows us to use the functions and features provided by NumPy throughout our code.

* First we search for the NumPY library on python package index website. https://pypi.org/project/numpy/

* Then we open our terminal and  type:::

    pip install numpy

If we already have a library installed on your system then it's going to skip the installation process.

* Start Python up and then, import NumPy and alias it to `np`, so type: ::

    import numpy as np 

    and hit return.

* Create an Array: 

    Type the following: ::

        num_range = np.arange(16)

    This creates an array called num_range containing integers from 0 to 15 (inclusive). The `arange()` function (inside NumPy library) generates a sequence of numbers with the specified range.

* Display the Array:

    When run `num_range`, we get the following output: ::

        array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15])

    This shows the elements of the array in a single row.

* Reshape the Array:
  
  Type this line: :: 

        num_range.reshape(4, 4) 

  It reshapes the original array into a array with dimensions 4x4 (4 rows and 4 columns).
  
  The resulting array looks like this: ::

        array([[ 0,  1,  2,  3],
            [ 4,  5,  6,  7],
            [ 8,  9, 10, 11],
            [12, 13, 14, 15]])


It's obviously possible to perform everything that we just did above in pure python code without a library, but we can see how much easier it is when we leverage outside tools.

NumPy arrays are more memory-efficient than Python lists, especially for large datasets.

You can go and look at the documentation and explore how many different functions and packages are available in NumPy here: https://numpy.org/doc/stable/user/absolute_beginners.html 

References and further reading about pip:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Visit the official website: https://pypi.org/project/pip/ 
https://www.freecodecamp.org/news/how-to-use-pip-install-in-python/
https://pip.pypa.io/en/stable/installation/  
https://basque.devcamp.com/pt-full-stack-development-javascript-python-react/guide/introduction-numpy-package-python


