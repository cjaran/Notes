# **Compile &amp; Execute**

**Run your Hello World C++ program locally using the Terminal, Command Prompt, or Visual Studio Code.**

**The Process**

C++ is a compiled language. That means that to get a program to run, you must first translate it from the human-readable form to something a machine can &quot;understand.&quot; That translation is done by a program called a _compiler_.

What you read and write is called _source code_ (usually it&#39;s in an English-like language like C++), and what the computer executes is called _executable_, _object code_, or _machine code_ (a machine language).

Typically C++ source code files are given the suffix:

- **.cpp**  (ex:  **hello.cpp** ) or
- **.h**  (ex:  **std\_lib\_facilities.h** ).

![](RackMultipart20201123-4-1xkxs8n_html_ee8217051bd33b54.png)

**Compile:**

g++ hello.cpp -o hello

A compiler translates the C++ program into machine language code which it stores on the disk as a file with the extension  **.o**  (e.g.  **hello.o** ). A linker then links the object code with standard library routines that the program may use and creates an executable image which is also saved on disk, usually as a file with the file name without any extension (e.g.  **hello** ).

**Execute:**

./hello

The executable is loaded from the disk to memory and the computer&#39;s CPU ( **C** entral  **P** rocessing  **U** nit) executes the program one instruction at a time.

**Running Hello World Locally:**

On the Mac, it&#39;s called the Terminal. On Windows, it&#39;s called the Command Prompt.

![](RackMultipart20201123-4-1xkxs8n_html_db3a09efd7a1497.png)
