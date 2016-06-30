# Conditionals
### An Introduction

Conditionals are built into our daily lives, even if largely unnoticed.  The definition is simple, conditional statements are "subject to one or more conditions or requirements being met."  In speech, we use conditionals fairly often.  

* "If it rains today, I will use my umbrella."
* "I will say hello if we see each other"

In mathematics, conditionals are the foundation for many complex proofs.  This is done through logic statements that can be used to further mathematical arguments.

In programming, conditionals follow a similar role where developers seek to run certain code under very specific instances.  Such instances can be achieved using ***if statements***.  

In this tutorial, we will cover the fundamentals of conditional statements in development.  We will be using Python as the primary language in this tutorial, although the concepts are consistent throughout all largely used programming languages. 

### If Statements
*We will assume an understanding of basic operators (+, -, +=, <, >, %, and, or, ==).  Please see this tutorial for an introduction to operators used in programming languages*

The "if statement" is built into programming languages and is used to execute code when certain conditions are met.

In Python, an if statement looks as follows:

```
if condition:
    <Indented Code Block>
```

An if statement requires one input, also called a *parameter*.  This parameter must be of type *Boolean*.  A Boolean is a data type that can only have two values: TRUE or FALSE.  

So, if the condition in the above code were true, then the indented code block would be executed.

Here's a real example of a Python if statement:

```
x = 5

if x < 10:
    x += 10
print x
```
**Returns**
```
15
```

We began by defining a variable ```x``` to be an integer with value 5.  The parameter for our if-statement was a check to see if ```x``` was less than 10.  This returned TRUE, allowing the next line to be executed, adding a value of 10 to ```x```.  The resulting value of ```x``` returned 15.

## Else Statements

When using if statements, it is common to have an *else* immediately following.  In speech, we recognize else statments as follows:

* "If it rains today, I will use my umbrella.  Otherwise, I will wear my sunglasses."

In this case, "Otherwise" is our "else", and "I will use my sunglasses" is the executed code. Let's see what this looks like in practice:

```
x = 0

if x == 5:
    x += 10
else:
    x += 100
    
print x
```   
**Returns**
```
100
```
Unlike the previous example, ```x``` is initially set to 0.  Now, our first if statement will process a FALSE, thereby not executing ```x += 10```.  Instead, our program will process the "else:" statement, ```x += 100```, giving a final value of 100 to ```x```.

## Else If Statements

In some cases, we might want to only execute code under two different situations.  For example:
* "If it rains today, I will use my umbrella. Otherwise, if it's sunny, I'll wear my sunglasses."

The last time we used this example in the previous section, if it weren't raining, then I would always wear my sunglasses.  However, the difference now is the second if clause.  Now, if it's not raining, I'll only wear my sunglasses if it's also sunny.

Let's see if it makes more sense written in Python.  Python uses the shorthand ***elif*** for else if statements.

```
x = 0

if x == 5:
	x += 10
elif x == 0:
	x += 5
    
print x
```
**Returns**
```
5
```
The first if clause returns FALSE, because ```x``` is not equal to 5.  However, our "elif" contains a clause checking if ```x``` is equal to 0.  In this case, this is TRUE.  As a result, the following line's code is executed, adding the value 5 to ```x```.  The end result is a value of 5 for ```x```.

## Multiple Clauses

If statements can be very powerful as they are expressed above.  However, programmers can also have multiple cases within a single if.  This drastically increases the functionality of if-statements, allowing for a multitude of test cases.  In speech, we say:
* "If it rains or it's not sunny, then I will not wear my sunglasses."

Notice the use of the word ***or***, which separates the two Boolean expressions: "it rains" and "it's not sunny".

In programming, "or" can be denoted by several symbols, most usually a double pipe: ```if a || b``` evaluates to TRUE if either a or b is TRUE (Also evaluates to TRUE if both a and b are TRUE).  

In Python, || was replaced with the "or" operator for readability.  So let's look at an example:

```
x = 0

if x == 5 or x == 0:
	x += 10
else:
	x += 5
    
print x
```
**Returns**
```
10
```
By including the second clause in our first if-statement, we then get a result of TRUE, allowing ```x += 10``` to be executed.

We can also use the operator ***and*** in the same way:

```
x = 0

if x == 5 and x == 0:
	x += 10
else:
	x += 5
    
print x
```
**Returns**
```
5
```
Of course, a number cannot be equal to both 5 and 0, so our first if clause returns FALSE.  As a result, we execute the code under our "else:", ```x += 5```, giving a final value of 5 to ```x```.

## Examples
Sometimes it might be difficult to see how exactly if-statements work.  So here are a few exampels of if-statements and their results.  Try and guess what each "print x" returns!

**Example 1**
```
x = 10

if x == 5 and x == 0:
	x += 10
elif x < 100:
	x += 100
    
print x
```
**Returns**
```
110
```
Our first if clause returns FALSE.  We then move to our "elif", which evaluates to TRUE.  As a result, we execute the code ```x += 100```.

**Example 2**
```
x = 10

if (x == 5 and x == 0) or x == 10:
	x += 10
elif x < 100:
    x += 100
    
print x
```
**Returns**
```
20
```
Here we see the stringing of multiple and/or operators in a single if-statement.  although the first part of the clause, ```x == 5 and x == 0``` evaluates to FALSE, the second part, ```x == 10``` evaluates to TRUE.  This makes our entire if clause true, and so we execute the code ```x = 10 ```.

**Example 3**
```
x = 22

if x < 100 and x > 10:
	x = 10
else:
    x += 100

if x == 10:
    x += 100
    
print x
```
**Returns**
```
110
```
Here, we see the use of two if-statements.  In the first block, we check if ```x < 100 and x > 10```.  This evaluates to TRUE, so we then set ```x = 10```.  We skip over the else statement, and move onto the next if.  Here, we check if ```x == 10```.  This returns TRUE, and so we add 100 to ```x```, leaving a value of 110.  

## Conclusion
So hopefully you find that if-statements are incredibly powerful in programming.  That said, too many if-statements can end up looking clunky to those trying to read code.  This can be helped by making sure if-statements are used only when needed, and are used efficiently.








