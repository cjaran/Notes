# Contents

[Introduction to Conditionals &amp; Logic 1](#_Toc56960961)

[If Statement 1](#_Toc56960962)

[Relational Operators 2](#_Toc56960963)

[Else Clause 2](#_Toc56960964)

[Else If 3](#_Toc56960965)

[Switch Statement 4](#_Toc56960966)

[Here are some of the major concepts: 5](#_Toc56960967)

[Introduction to Logical Operators 5](#_Toc56960968)

[Logical Operator: &amp;&amp; 6](#_Toc56960969)

[Logical Operator: II 6](#_Toc56960970)

[Logical Operator: ! 7](#_Toc56960971)

## Introduction to Conditionals &amp; Logic

Every program we&#39;ve seen so far has only had one possible path of execution — they all execute line by line, from top to bottom. And every time you run one of those programs, it gives you the same exact result. But it&#39;s the twenty-first century, and we like options!

In this lesson, we will explore how programs make decisions by evaluating conditions and introduce logic into our code!

We&#39;ll be covering the following concepts:

- if, else if, and else statements
- switch statements
- Relational operators
- Logical operators

So… _if_ you&#39;ve already learned these concepts in another language, go to the next lesson — _else_, prepare yourself and let&#39;s get started!

## If Statement

An if statement is used to test an expression for truth and execute some code based on it. Here&#39;s a simple form of the if statement:

if (condition) {

some code

}

If the _condition_ is true, then the _statements_ within are executed. Otherwise, the _statements_ are skipped and the program continues on.

if (flip == 1) {

  std::cout \&lt;\&lt; &quot;Heads\n&quot;;

}

The if keyword is followed by a set of parentheses (). Inside the parentheses (), a condition is provided that evaluates to true or false:

- If the condition evaluates to true, the code inside the curly braces {} executes.
- If the condition evaluates to false, the code won&#39;t execute.

So in the code above, if flip is equal to 1, the program outputs &quot;Heads&quot;; if it does not, then nothing happens and the program continues.

## Relational Operators

When writing conditional statements, sometimes we need to use different types of operators to compare values. These operators are called _relational operators_.

To have a condition, we need relational operators:

- == equal to
- != not equal to
- \&gt; greater than
- \&lt; less than
- \&gt;= greater than or equal to
- \&lt;= less than or equal to

Relational operators compare the value on the left with the value on the right.

## Else Clause

We can also add an else clause to an if statement to provide code that will only be executed if the condition is false. Here&#39;s a form of an if statement that includes an else clause:

if (condition) {

do something

} else {

do something else

}

- If _condition_ is true, _statement1_ is executed. Then the program _skips_ _statement2_ and executes any code statements following the if/else clause.
- If _condition_ is false, _statement1_ is _skipped_ and _statement2_ is executed. After _statement2_ completes, the program executes any code statements following the if/else clause.

if (coin == 1) {

  std::cout \&lt;\&lt; &quot;Heads\n&quot;;

}
else {

  std::cout \&lt;\&lt; &quot;Tails\n&quot;;

}

So in the code above, if coin is equal to 1, the program outputs &quot;Heads&quot;; if it does not, then it outputs &quot;Tails&quot;.

**Note:**  It&#39;s either or — only one of them will execute!

## Else If

So, what happens if you want more than two possible outcomes?

This is where else if comes in!

if (condition) {

some code

} else if (condition) {

some code

} else {

some code

}

The else if statement always comes after the if statement and before the else statement. The else if statement also takes a condition.

And you can have more than one of them! Here&#39;s an example with three of them:

if (grade == 9) {

  std::cout \&lt;\&lt; &quot;Freshman\n&quot;;

}
elseif (grade == 10) {

  std::cout \&lt;\&lt; &quot;Sophomore\n&quot;;

}
elseif (grade == 11) {

  std::cout \&lt;\&lt; &quot;Junior\n&quot;;

}
elseif (grade == 12) {

  std::cout \&lt;\&lt; &quot;Senior\n&quot;;

}
else {

  std::cout \&lt;\&lt; &quot;Super Senior\n&quot;;

}

## Switch Statement

Now that we know how if, else if, else work, we can write programs that have multiple outcomes. Programs with multiple outcomes are so common that C++ provides a special statement for it… the switch statement!

A switch statement provides an alternative syntax that is easier to read and write. However, you are going to find these less frequently than if, else if, else in the wild.

A switch statement looks like this:

switch (grade) {

  case9:
    std::cout \&lt;\&lt; &quot;Freshman\n&quot;;
    break;
  case10:
    std::cout \&lt;\&lt; &quot;Sophomore\n&quot;;
    break;
  case11:
    std::cout \&lt;\&lt; &quot;Junior\n&quot;;
    break;
  case12:
    std::cout \&lt;\&lt; &quot;Senior\n&quot;;
    break;
  default:
    std::cout \&lt;\&lt; &quot;Invalid\n&quot;;
    break;

}

- The switch keyword initiates the statement and is followed by (), which contains the value that each case will compare. In the example, the value or expression of the switch statement is grade. One restriction on this expression is that it must evaluate to an integral type (int, char, short, long, long long, or enum).
- Inside the block, {}, there are multiple cases.
- The case keyword checks if the expression matches the specified value that comes after it. The value following the first case is 9. If the value of grade is equal to 9, then the code that follows the : would run.
- The break keyword tells the computer to exit the block and not execute any more code or check any other cases inside the code block.
- At the end of each switch statement, there is a default statement. If none of the cases are true, then the code in the default statement will run. It&#39;s essentially the else part.

In the code above, suppose grade is equal to 10, then the output would be &quot;Sophomore&quot;.

**Note:**  Without the break keyword at the end of each case, the program would execute the code for the first matching case and _all_ subsequent cases, including the default code. This behavior is different from if / else conditional statements which execute only one block of code.

## Here are some of the major concepts:

- An if statement checks a condition and will execute a task if that condition evaluates to true.
- if / else statements make binary decisions and execute different code blocks based on a provided condition.
- We can add more conditions using else if statements.
- Relational operators, including \&lt;, \&gt;, \&lt;=, \&gt;=, ==, and != can compare two values.
- A switch statement can be used to simplify the process of writing multiple else if statements. The break keyword stops the remaining cases from being checked and executed in a switch statement.

## Introduction to Logical Operators

Often, when we are trying to create a control flow for our program, we&#39;ll encounter situations where the logic cannot be satisfied with a single condition.

_Logical operators_ are used to combine two or more conditions. They allow programs to make more flexible decisions. The result of the operation of a logical operator is a bool value of either true or false.

There are three logical operators that we will cover:

- &amp;&amp;: the and logical operator
- ||: the or logical operator
- !: the not logical operator

We will also discuss the order of operations.

Let&#39;s get started!

## Logical Operator: &amp;&amp;

The and logical operator is denoted by &amp;&amp;.

It returns true if the condition on the left _and_ the condition on the right are both true. Otherwise, it returns false.

Here&#39;s the truth table:

| **a** | **b** | **a &amp;&amp; b** |
| --- | --- | --- |
| false | false | false |
| --- | --- | --- |
| false | true | false |
| true | false | false |
| true | true | true |

For instance:

- ( 1 \&lt; 2 &amp;&amp; 2 \&lt; 3 ) returns true
- ( 1 \&lt; 2 &amp;&amp; 2 \&gt; 3 ) returns false

**Note:**  The keyword and can also be used in the place of &amp;&amp;.

## Logical Operator: II

The or logical operator is denoted by ||.

It returns true when the condition on the left is true _or_ the condition on the right is true. Only one of them needs to be true.

Here&#39;s the truth table:

| **a** | **b** | **a || b** |
| --- | --- | --- |
| false | false | false |
| --- | --- | --- |
| false | true | true |
| true | false | true |
| true | true | true |

For instance:

- ( 1 \&lt; 2 || 2 \&gt; 3 ) returns true
- ( 1 \&gt; 2 || 2 \&gt; 3 ) returns false

**Note:**  The keyword or can be used in the place of ||.

## Logical Operator: !

The not logical operator is denoted by !.

It reverses the bool outcome of the expression that immediately follows.

Here&#39;s the truth table:

| **a** | **!a** |
| --- | --- |
| false | true |
| --- | --- |
| true | false |

For instance:

- ( !true ) returns false
- ( !false ) returns true
- ( !(10 \&lt; 11) ) returns false

**Note:**  The keyword not can be used in the place of !.

 In this mini-lesson, we&#39;ve added more operators to our toolbox:

- &amp;&amp;: the and logical operator
- ||: the or logical operator
- !: the not logical operator
