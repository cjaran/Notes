# Contents

[Introduction to Vectors 1](#_Toc57013197)

[Creating a Vector 1](#_Toc57013198)

[Initializing a Vector 2](#_Toc57013199)

[Vector Index 3](#_Toc57013200)

[Adding and Removing Elements 3](#_Toc57013201)

[.size() 4](#_Toc57013202)

[Operations 5](#_Toc57013203)

## Introduction to Vectors

To do just about anything of interest in a program, we need a group of data to work with.

For example, our program might need:

- A list of Twitter&#39;s trending tags
- A set of payment options for a car
- A catalog of eBooks read over the last year

The need for storing a collection of data is endless.

We are familiar with data types like int and double, but how do we store a group of ints or a group of doubles?

In this lesson, we will start with one of the simplest, and arguably the most useful, ways of storing data in C++: a vector.

A _vector_ is a sequence of elements that you can access by index.

## Creating a Vector

The std::vector lives in the \&lt;vector\&gt; header. So first, we need to add this line of code at the top of the program:

#include\&lt;vector\&gt;

For review, #include is a preprocessor directive that tells the compiler to include whatever library that follows. In our case that is the standard vector library.

And the syntax to create a vector looks like:

std::vector\&lt;type\&gt;name;

So to define a vector of ints called calories\_today:

std::vector\&lt;int\&gt;calories\_today;

Inside the angle brackets is the data type of the vector. After the angle brackets is the name of the vector.

**Note:**  The type of the vector (i.e., what data type is stored inside) cannot be changed after the declaration.

## Initializing a Vector

Now we know how to create a vector, we can also initialize a vector, giving it values, as we are creating it in the same line.

For example, instead of just creating a double vector named location:

std::vector\&lt;double\&gt;location;

We can create _and_ initialize location with specific values:

std::vector\&lt;double\&gt;location = {42.651443, -73.749302};

Here, we are storing [a latitude and a longitude](https://en.wikipedia.org/wiki/Geographic_coordinate_system).

So it would look something like this:

![](RackMultipart20201123-4-1miauge_html_f551efbbde286854.png)

Another way we can initialize our vector is by _presizing_, or setting the size.

Suppose we want to create and initialize a vector with two elements. However, we don&#39;t know what values we want to add yet:

std::vector\&lt;double\&gt;location(2);

Here, we are creating a double vector and setting the initial size to two using parentheses.

It would look something like this:

![](RackMultipart20201123-4-1miauge_html_d8152ff508bbad29.png)

Because 0.0 is the default value for double.

## Vector Index

Now that we have a vector, how do we access an individual element? This is where index comes into play.

An _index_ refers to an element&#39;s position within an ordered list. Vectors are 0-indexed, meaning the first element has index 0, the second index 1, and so on.

For example, suppose we have a char vector with all the [vowels](https://en.wikipedia.org/wiki/Vowel):

std::vector\&lt;char\&gt;vowels = {&#39;a&#39;, &#39;e&#39;, &#39;i&#39;, &#39;o&#39;, &#39;u&#39;};

It should look something like this:

![](RackMultipart20201123-4-1miauge_html_cadcf55c13a42782.png)

- The character at index 0 is &#39;a&#39;.
- The character at index 1 is &#39;e&#39;.
- The character at index 2 is &#39;i&#39;.
- The character at index 3 is &#39;o&#39;.
- The character at index 4 is &#39;u&#39;.

To output each of the elements, we can do:

std::cout \&lt;\&lt; vowels[0] \&lt;\&lt; &quot;\n&quot;;
std::cout \&lt;\&lt; vowels[1] \&lt;\&lt; &quot;\n&quot;;
std::cout \&lt;\&lt; vowels[2] \&lt;\&lt; &quot;\n&quot;;
std::cout \&lt;\&lt; vowels[3] \&lt;\&lt; &quot;\n&quot;;
std::cout \&lt;\&lt; vowels[4] \&lt;\&lt; &quot;\n&quot;;

Using the notation vector[index] with square brackets after the vector name and the element&#39;s index number inside.

This will output:

a
e
i
o
u

## Adding and Removing Elements

Often, we start with a vector that&#39;s either empty or a certain length. As we read or compute data we want, we can grow the vector as needed.

##### .push\_back()

To add a new element to the &quot;back&quot;, or end of the vector, we can use the .push\_back() function.

For example, suppose we have a vector called dna with three letter codes of [nucleotides](https://en.wikipedia.org/wiki/Nucleotide):

std::vector\&lt;std::string\&gt;dna = {&quot;ATG&quot;, &quot;ACG&quot;};

It would look like:

![](RackMultipart20201123-4-1miauge_html_85b27b8857a9e623.png)

We can add elements using .push\_back():

dna.push\_back(&quot;GTG&quot;);

So now dna would look like:

![](RackMultipart20201123-4-1miauge_html_274436761765b876.png)

##### .pop\_back()

You can also remove elements from the &quot;back&quot; of the vector using .pop\_back().

dna.pop\_back();

Notice how nothing goes inside the parentheses.

The vector would now look like:

![](RackMultipart20201123-4-1miauge_html_2d9a67e89c6879a4.png)

because CTG is removed!

**Note:**  If you have programmed in other languages, be aware that .pop\_back() has no return value in C++.

## .size()

\&lt;std::vector\&gt; not only stores the elements; it also stores the size of the vector:

![](RackMultipart20201123-4-1miauge_html_51da3f98a2aaaa1e.png)

The .size() function returns the number of elements in the vector.

For example, suppose we have a std::string vector with Sonny&#39;s grocery list:

std::vector\&lt;std::string\&gt;grocery = {&quot;Hot Pepper Jam&quot;, &quot;Dragon Fruit&quot;, &quot;Brussel Sprouts&quot;};

It should look something like this:

![](RackMultipart20201123-4-1miauge_html_9c0813c172251a2.png)

- The string at index 0 is &quot;Hot Pepper Jam&quot;.
- The string at index 1 is &quot;Dragon Fruit&quot;.
- The string at index 2 is &quot;Brussel Sprouts&quot;.

std::cout \&lt;\&lt; grocery.size() \&lt;\&lt; &quot;\n&quot;;

will return

3

Notice how nothing goes in the parentheses.

## Operations

So what happens when you want to change each of the values within a vector?

You can use a for loop!

For example, suppose we have an int vector that looks like this:

![](RackMultipart20201123-4-1miauge_html_f81c3b88ee09f550.png)

You can write a for loop that iterates from 0 to vector.size(). And here&#39;s the cool part: you can use the counter of the for loop as the index! Woah.

for (inti = 0; i\&lt;vector.size(); i++) {

  vector[i] = vector[i] + 10;

}

This will change the vector to:

![](RackMultipart20201123-4-1miauge_html_cb4b7108ad4640b3.png)

Here, we incremented i from 0 to vector.size(), which is 3. During each iteration, we are adding 10 to the element at position i:

- When i = 0, we added 10 to vector[0]
- When i = 1, we added 10 to vector[1]
- When i = 2, we added 10 to vector[2]

## Review

Congratulations! You have learned about how to store groups of data into vectors in C++. 🙌

Here are some of the things that we learned:

-   Vectors are a sequence of elements that you can access by an index.

    ```
    std::vector<int> even = {2, 4, 6, 8, 10};
    ```

-   The first index in a vector is `0`.

-   Some of the functions that come with vectors:

    -   `.push_back()`
    -   `.pop_back()`
    -   `.size()`
-   We can use a `for` loop to iterate through a vector.