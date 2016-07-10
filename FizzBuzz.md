# FizzBuzz
## An Introduction

Commonly, companies that employ technical interviews within their hiring process include simple programming challenges to ensure a basic understanding of common technical fundamentals.

One such example, ***FizzBuzz***, is a simple programming challenge that has its origin in an arithmetic exercise to familiarize children with divisibiliy rules.  The text for the FizzBuzz problem states

 * *Write a program that prints the numbers from 1 to 100. For multiples of three print “Fizz” instead of the number and for multiples of five print “Buzz”. For numbers which are multiples of both three and five print “FizzBuzz”.*

So if we were to run this program, our first few responses would be as follows:

* *1 , 2 , Fizz , 4 , Buzz , Fizz , 7 , 8 , Fizz , Buzz , 11 , Fizz , 13 , 14 , FizzBuzz , 16...*

## Thinking Through It
The first step in solving a problem like this involves thinking through the solution as if you were asked to speak FizzBuzz aloud.

Given any number, we first ask the following questions:

* **Q1 -** *Is this number divisible by 3?*
    *   1 - NO
    *   13 - NO
    *   30 - YES
    *   55 - NO
    *   99 - YES

* **Q2 -** *Is this number divisible by 5?*
  * 1 - NO
  * 13 - NO
  * 30 - YES
  * 55 - YES
  * 99 - NO
  
With both questions, there are two possible outcomes: YES and NO.  Now, let's take a look at what the responses were for all of the numbers we've used:

* **1:**  NO, NO
* **13:** NO, NO
* **30:** YES, YES
* **55:** NO, YES
* **99:** YES, NO

With our 5 examples, we have covered all possible combinations of answers to our initial questions.  We can see that there are 4 cases to determine our response.  Let's cover these cases below:

**Case 1: NO, NO**

*This is the case where the number is neither divisible by 3 or 5. (1, 2, 4, 7, ...)*

In this case, we simply say the number as is because it fails to meet the requirements for Fizz, Buzz, or FizzBuzz.

**Case 2: YES, NO**

*This is the case where the number is divisible by 3, but not 5. (3, 6, 9, 12, ...)*

In this case, the number meets the "Fizz" requirement, and so we substitute the number for Fizz.

**Case 3: NO, YES**

*This is the case where the number is divisible by 5, but not 3. (5, 10, 20, 25,...)*

In this case, the number meets the "Buzz" requirement, and so we substitute the number for Buzz.

**Case 4: YES, YES**

*This is the case where the number is divisible by both 3 and 5. (15, 30, 45, 60,...)*

In this case, the number meets the "FizzBuzz" requirement, and so we substitute the number for FizzBuzz.

In sum, our program must account for the 4 different end results for our two initial questions.  In the next section, we will use multiple "if" statements as a basis for our implementation.

## Implementation
*In this tutorial, we will be using the [Python](https://www.python.org) programming language.  Python is a widely used programming language that is known for its readable syntax, so it is used commonly for short programming tests such as FizzBuzz.  Please make sure that your development environment is setup with Python installed.  The [following](http://docs.python-guide.org/en/latest/starting/installation/) is a good tutorial to help you download Python.*

In looking at the original problem, we are told to apply our FizzBuzz cases to the numbers from 1 to 100.  Because of this range, we can start with a "*for loop*".  A for loop will allow us to run the same test cases against a large set of numbers, in this case the set from 1 to 100.

The for loop we will be using looks like this:

```
for num in range(1,101):
    <Code goes here>
```

For a number - ```num``` - starting from 1 and ending at 100, execute ```<Code goes here>```. ```num``` is our variable here, and our range is 1 to 101, exclusive at 101.

Now we will work inside our for loop.  Our first step might seem unnecessary, but we will need to define an empty String (a String is a collection of keyboard characters).

```
for num in range(1,101):
    response = ""
```

The reason for doing so is that ```response``` is the variable that we will eventually print for each number from 1 to 100.  What ```response``` is set to depends on the number we are looking at.  Right now, printing ```response``` would return an empty String.

Now comes the test cases for each number.  Let's go in order of the questions we had written in the previous section, starting with our divisibility by 3 check:

```
for num in range(1,101):
    response = ""
    if num % 3 == 0:
        response += "Fizz"
```

In the two lines added, we begin with an *"if statement"*, which uses the mathematical symbol *modulo* (%), which is our divisibility check.  ```num % 3``` returns the remainder when ```num``` is divided by 3. If our number is divisible by 3, then ```num % 3``` will return 0.  If that is the case, we will add the characters "Fizz" to```response```.  This is done using the ```+=``` operator.

Our next if statement will be our divisibility by 5 check:

```
for num in range(1,101):
    response = ""
    if num % 3 == 0:
        response += "Fizz"
    if num % 5 == 0:
        response += "Buzz"
```

At this point, we have covered 3 of the 4 cases we needed to.  The case where ```num``` meets the "Fizz" requirement, the case where ```num``` meets the "Buzz" requirement, and also the case where ```num``` meets the "FizzBuzz" requirement.  However, if the number did not meet any of the requirements, we need to set ```response``` to just be the current number.

This is done as follows:
```
for num in range(1,101):
    response = ""
    if num % 3 == 0:
        response += "Fizz"
    if num % 5 == 0:
        response += "Buzz"
    if response == "":
        response = num
```

If the number fits none of the FizzBuzz requirements, then response would have not changed from its initial definition ```response = ""```.  So our last if statement will check if ```response``` is empty, and if so it will be set equal to the current number.

Now we just print response!
```
for num in range(1,101):
    response = ""
    if num % 3 == 0:
        response += "Fizz"
    if num % 5 == 0:
        response += "Buzz"
    if response == ""':
        response = num
    print(response)
```
The difference in our last if statement is that we are redifining ```response``` to be an integer rather than a String, hence the single ```=``` operator.

### Conclusion

There are many different ways to implement the FizzBuzz coding question.  Many times, interviewers will use FizzBuzz to see if a programmer can write clean and efficient code.  Hopefully this tutorial can help kickstart a deeper exploration into more complicated coding problems, and can serve as a reference for some fundamental programming tools.  
