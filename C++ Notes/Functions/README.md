# Contents

[The Function of Functions 1](#_Toc57032177)

[Built-in Functions 2](#_Toc57032178)

[Declare &amp; Define 2](#_Toc57032179)

[Void — The Point of No Return 3](#_Toc57032180)

[Return Types — Beyond the Void 4](#_Toc57032181)

[How Return Values Work 4](#_Toc57032182)

[Parameters &amp; Arguments 5](#_Toc57032183)

[Tackling Multiple Arguments 6](#_Toc57032184)

[How Parameters &amp; Arguments Work 6](#_Toc57032185)

[Review of C++ Functions 7](#_Toc57032186)

## The Function of Functions

As a programmer, you will find yourself reusing the same blocks of code over and over throughout your program. In times like these, you can turn to functions.

Also known as a method or procedure, a _function_ is a named group of code statements that accomplish something together, a bit like a factory machine.

![](RackMultipart20201123-4-ely9qv_html_f5078a51beffb84c.gif)

There are some great reasons to use functions in your code:

- A single line can make all that code fire off instead of a whole bunch of lines.
- You can build DRY (Don&#39;t Repeat Yourself) code, reusing the code you already wrote.
- Functions help make your code flexible and _modular_, meaning you can group your code more easily by task.

In fact, every C++ program has at least one function. &quot;Hold on,&quot; you may be thinking, &quot;I&#39;ve written some C++ programs, but I haven&#39;t written any functions yet!&quot;

Well, as it happens, main() is a function that you&#39;ve already used! And you&#39;ll understand it a bit more as you learn how functions work.

## Built-in Functions

Before we learn how to create functions, let&#39;s go over some built-in functions…

C++ comes chock-full of functions that are already created as part of the standard library. But how do we access this hidden hoard of helpful functions? We gain access to various functions by including headers like \&lt;cmath\&gt; or \&lt;string\&gt;.

In fact, you may already have used a couple functions without even knowing it! With the following header:

#include\&lt;cmath\&gt;

We gain the power to call sqrt() to find the square root of any number.

Wait, &quot;call&quot; sqrt()?

_Calling_ a function is how we get a function to take action. To call a basic function, we just need the function name followed by a pair of parentheses like sqrt(9). For example:

std::cout \&lt;\&lt; sqrt(9) \&lt;\&lt; &quot;\n&quot;;

 // This would output 3

## Declare &amp; Define

Often, built-in functions aren&#39;t enough to tackle the wide array of programming challenges out there. But never fear: you can write your own functions too!

A C++ function is comprised of two distinct parts:

- _Declaration_: this includes the function&#39;s name, what the return type is, and any parameters (if the function will accept input values, known as arguments).
- _Definition_: also known as the _body_ of the function, this contains the instructions for what the function is supposed to do.

This is the overall structure:

return\_typefunction\_name( any, parameters, you, have ) {

   // Code block here

   returnoutput\_if\_there\_is\_any;

}

This is what it might look like with real code:

voidmake\_sandwich() {

  std::cout \&lt;\&lt; &quot;bread\n&quot;;
  std::cout \&lt;\&lt; &quot;egg\n&quot;;
  std::cout \&lt;\&lt; &quot;cheese\n&quot;;
  std::cout \&lt;\&lt; &quot;avocado\n&quot;;
  std::cout \&lt;\&lt; &quot;bread\n&quot;;

}

## Void — The Point of No Return

Let&#39;s build a simple function with no input and no output. We can do that?

Enter the void specifier, which is added in the function declaration before the function name. A void function, also known as a subroutine, has no return value, making it ideally suited for situations where you just want to print stuff to the terminal.

For example:

voidanimal\_chat() {

  std::stringfav, pet;

  std::cout \&lt;\&lt; &quot;What&#39;s your favorite animal?\n&quot;;
  std::cin \&gt;\&gt; fav;

  std::cout \&lt;\&lt; &quot;Do you have a &quot; \&lt;\&lt; fav \&lt;\&lt; &quot; as a pet? y/n\n&quot;;
  std::cin \&gt;\&gt; pet;

  if (pet == &quot;y&quot;) {

    std::cout \&lt;\&lt; &quot;How lucky you have a &quot; \&lt;\&lt; fav \&lt;\&lt; &quot; as a pet!\n&quot;;

  } else {

    std::cout \&lt;\&lt; &quot;That&#39;s too bad.\n&quot;;

  }

}

The above chat program is built to capture user responses and print to the terminal without returning any values.

## Return Types — Beyond the Void

When you do in fact want your function to return something and pass information back to the rest of your program, C++ has you covered. Just like there are many variable types, there are many different return types for functions.

A function can return most data types we&#39;ve covered, including double, int, bool, char, std::string, and std::vector.

std::stringalways\_blue() {

  return&quot;blue!\n&quot;;

}

**Note:**  The return statement is the last line of code that a function will execute. For example:

std::stringalways\_blue() {

  return&quot;blue!\n&quot;;

  std::cout \&lt;\&lt; &quot;Returned blue!&quot;;

}

The final line will not execute because a value has already been returned. So &quot;Returned blue!&quot; won&#39;t be printed to the terminal.

## How Return Values Work

When functions have a return type other than void, the function has two new requirements:

- There must be a value returned from the function.
- The return value must be the same type as the function&#39;s return type.

But where does the return value get returned to?

It gets returned to the place where the function is called. For example, if you have the following function:

std::stringfeed\_the\_cat() {

  return&quot;Cat is fed!&quot;;

}

And then print the function call inside of main():

intmain() {

  std::stringcat\_message = feed\_the\_cat();
  std::cout \&lt;\&lt; cat\_message;

}

The return value of the function is what gets printed to the terminal.

## Parameters &amp; Arguments

Returning data is all well and good, but let&#39;s say you&#39;re visiting NYC and you&#39;ve been told that New Yorkers usually add a 20% tip for restaurants and taxis. It would be really convenient if you could just build a function that accepted different prices as input and figured out how much you should tip.

As it happens, you can do that with parameters. _Parameters_ (sometimes called _formal parameters_) are variables used in a function&#39;s definition. They act as placeholders for the input values you&#39;ll use during your function call.

![](RackMultipart20201123-4-ely9qv_html_7cd3138d0be528fe.gif)

In the function below, price is the function&#39;s parameter and it&#39;s a double. It is declared between the parentheses and then used in the body of the function.

doubleget\_tip(doubleprice) {

  returnprice \* 0.2;

}

Then, when you&#39;re ready to use your function, the value you pass to the function is called an _argument_ (also known as an _actual parameter_). In this case, 15.75 is the argument that is passed to the function:

doubletip = get\_tip(15.75);
 // tip would be 3.15

## Tackling Multiple Arguments

Hang on, you may be thinking, are you limited to one parameter per function? Not at all! You can add as many as you like, but you will have to remember their order when you call the function.

doubleget\_tip(doubleprice, doubletip, booltotal\_included) {

  if (total\_included) {

    returnprice \* tip + price;

  } else {

    returnprice \* tip;

  }

}

So here we have three parameters:

- double price
- double tip
- bool total\_included

When calling get\_tip(), it&#39;s important to call it with price first, tip second, and return\_total last:

get\_tip(0.25, true, 45.50);
 // this code will not work

get\_tip(45.50, 0.25, true);
 // this code results in 56.875, which you could round up to 56.88

## How Parameters &amp; Arguments Work

A function with parameters has a couple of requirements:

- The function call must include the  **same number**  of arguments as there are parameters.
- The corresponding arguments must be passed in the  **same order**.

By calling a function with arguments, you are telling a function, &quot;Hey function, when you execute, use these values where you have parameters in your definition.&quot;

While it executes, anywhere the function comes across a parameter, it replaces the parameter with the corresponding argument you gave it.

## Review of C++ Functions

Check out all you&#39;ve learned about C++ functions:

- A function is a named group of statements that do something together.
- Functions allow you to create more flexible, modular, and DRY code.
- C++ has many built-in functions that you can use.
- Functions are called like function\_name();
- A function has a declaration with a return type and possible parameters.
- A function has a definition (or body) with a group of statements and a possible return value.
- void functions do not have return values.
- Functions with a return value have return statements.
- Parameters are variables used as placeholders for function input values.
- Arguments are a function&#39;s actual input values.

You now know enough C++ to create some pretty cool projects on your own. But, as you&#39;ll see, there are still many ways to improve your code.
