# Scala Setup

## Setting up your Scala toolchain

I will provide installation instructions for OSX, Linux (Ubuntu), and
Windows.

#### Homebrew [OSX only] 
 
Homebrew is a package manager for OSX, which makes installing
development software much easier. We will use it to install Sbt. You
will find it useful in the future for install of other things as well.

* [OSX] Install using the instructions [here](http://brew.sh/)

#### XCode [OSX only]

XCode is a development environment for Macs. We will not be using it,
but installing it installs a number of useful Unix command line tools.

* [OSX] Install the most recent version of XCode from [here](https://developer.apple.com/xcode/downloads/)

#### Git

* [Ubuntu] Git is pre-installed on Ubuntu.
* [OSX] From terminal: ```brew install git```
* You can test the install of git on your system by running the command `git` from terminal. You should see usage information.
* Finally run the following commands from terminal:<br>
   ```git config --global user.email "your@email.com"```<br>
   ```git config --global user.name "Your Name"```<br>
   (The email should be the same email you used to register your github account)
* [Windows] There are various Git tools available for Windows. You
  can also use the IntelliJ integration to interact with Git (see below).

Here are some Git-related resources:
* If you are unfamiliar with Git, watch the [first two git basics video](http://git-scm.com/videos).
* If you are unfamiliar with Github, watch [this YouTube video](https://www.youtube.com/watch?v=0fKg7e37bQE).
* A [simple git cheatsheet](http://rogerdudler.github.io/git-guide/).
* A [complete reference](http://www.git-scm.com/book/en/v2).
* I suggest using the command line or the IntelliJ integration to interact with Git, but in a pinch [this GUI](https://desktop.github.com/) might be useful.

#### Java Development Kit

We will need the Java Development Kit (JDK) to run Sbt and Scala programs.

* [Ubuntu] From terminal: ```sudo apt install default-jdk```
* [OSX] From terminal: ```brew cask install java```
* [Windows]
  Go
  [here](https://docs.oracle.com/en/java/javase/11/install/installation-jdk-microsoft-windows-platforms.html#GUID-A7E27B90-A28D-4237-9383-A58B416071CA) and
  follow the installation instructions.

#### Sbt

Sbt is an open source build tool for Scala projects. More information can be
found [here](https://en.wikipedia.org/wiki/SBT_%28software%29). (You
will need this to compile and run Scala code that I provide)

* [OSX]  From terminal: ```brew install sbt```
* [Ubuntu] From terminal:<br>
   ```echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list```<br>
   ```sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 642AC823```<br>
   ```sudo apt-get update```<br>
   ```sudo apt-get install sbt```  
* Confirm success by running the command from terminal: 
    ```sbt    ```
    (Sbt should start. Use `Ctrl+c` to quit or type `exit`.)
* [Windows] I suggest to use the Sbt integration provided by IntelliJ Idea
  (see below).

More detailed instructions can be found [here](http://www.scala-sbt.org/release/tutorial/Installing-sbt-on-Linux.html).


#### IntelliJ Idea

I will be using
the [IntelliJ Idea Java IDE](https://www.jetbrains.com/idea/) to
demonstrate Scala code in class. While it is not necessary
for you to install an IDE, I recommend using it as it will make your
life easier.

* Sign up
  for
  [free student licenses](https://www.jetbrains.com/shop/eform/students) (Reminder:
  use your NYU email address)
* In the meantime, download the [Ultimate Edition Free 30-day trial](https://www.jetbrains.com/idea/download/) of Intellij.
* [Ubuntu] Untar the downloaded archive by clicking it and then using the "Extract" menu item. Extract to location of your choice. Open that location and follow the instructions inside the "Install-Linux-tar.txt" file.
* [OSX] Open the disk image and use the installer.
* [Windows] Open the installer.
* When prompted, select "Evaluate for 30 days". Install the license when you get them in an email from Jetbrains.
* During the "Customize" phase on the "*Featured* plugins screen",
  select and install the 'Scala' plugin. It should be in the top left
  corner of this screen. This is necessary to get sbt integration and
  Scala support in Intellij.
* For reference, here is a link to the [Intellij documentation](https://www.jetbrains.com/idea/help/basic-concepts.html).

There are many free plugins available for IntelliJ. You should feel free to install anything that sounds useful to you. You can explore what is available from the "Preferences" menu in IntelliJ.

#### Importing a Scala Sbt Project into Intellij

To import the Scala Sbt project for Class 3 into IntelliJ, do the following:

* Choose a place on your computer for your project files to reside and open a terminal to that location.

* Manual Git clone [Ubuntu, OSX] 
  * Clone this repository from Github by executing the following git
    command in your terminal: <br/>
    ```git clone https://github.com/nyu-pl-sp19/class03.git```

  * Open IntelliJ and click the "Import Project" menu item
    (Alternatively, press Ctrl+Shift+a [Ubuntu] or Command+Shift+a [OSX]
    and type 'import project'. Then select the command 'Import Project'
    from the drop down menu).
  
  * Navigate to your cloned repository and select the "class02"
    directory and click "Import".
  
  * Click the radio button "Import project from external model".

  * Highlight sbt. Click Next.

  * Continue as described below.
  
* Git clone via IntelliJ git integration [Windows, Ubuntu, OSX]

  * Open IntelliJ and select "File/New/Project From Version
    Control/Git" from the main menu. Alternatively, if you are on the
    IntelliJ welcome screen, select "Check out from Version
    Control/Git".
    
  * Put ```https://github.com/nyu-pl-sp19/class03.git``` into the URL
    field and select the local directory where you want the repository
    to reside. 
    
  * Click "Clone".
  
  * Click "Import sbt project" in the pop up window.
  
  * Continue as described below.

* Setting up the sbt project in IntelliJ [all platforms]

  * Check "Use sbt shell for build and import", and under "Download:
    check "Library sources" and "sbt sources". Do not hit "Finish" yet.
  
  * The dropdown for the Project SDK might be empty. We
    need to configure a JVM.
  
    * Click "New" and then "JDK". 
    * Most likely IntelliJ will guess correctly where your JDK is. If not...
      * [Ubuntu] it is ```/usr/lib/jvm/java-10-openjdk-amd64``` or similar
        depending on your JDK version.
      * [OSX] Where your JVM is depends on what version of OSX you are
        using. On newer versions of OSX you can use this command to find
        the location of the JDK ```/usr/libexec/java_home -v 1.10```).
      * [Windows] Where your JVM is depends on what version of the JDK
        you have installed. On my machine it is in ```C:\Program
        Files\Java\jdk1.8.0_181\bin``` and you should find it in a
        similar directory on your machine.
      * Select the JDK folder.
    
  * Under "JVM Options" below "Global sbt settings", remove the text in
    the field labeled "VM parameters". Click "Finish".

  * It may take IntelliJ a few minutes to initialize the project as it
    will download all Scala dependencies and compile various parts of
    the Scala build infrastructure. Future project imports will be
    faster.

  * If you are prompted with a message like "Unregistered VCS root
    detected", simply click "Add root".

* Open the worksheet `src/main/scala/pl/class03/demo.sc` and type in
  some Scala expressions (see below). Alternatively, start the Scala
  REPL by typing `console` in the sbt shell. If the sbt shell is not
  already open, you can open it by pressing Crtl+Shift+s
  [Ubuntu,Windows] or Command+Shift+s [OSX].

* Post on Piazza if you need help, most likely others have had the
  same problem and may have figured it out.

## Scala Basics

In the following, we assume that you have started the Scala
REPL. Though, (almost) all of these steps can also be done in a Scala
worksheet.

#### Expressions, Values, and Types

After you type an expression in the REPL, such as `3 + 4`,
and hit enter:

```scala
scala> 3 + 4
```

The interpreter will print:

```scala
res0: Int = 7
```

This line includes:

* an automatically generated name `res0`, which refers
  to the value resulting from evaluating the expression,
* a colon `:`, followed by the type `Int` of the expression,
* an equals sign `=`,
* the value `7` resulting from evaluating the expression.

The type `Int` names the class `Int` in the
package `scala`. Packages in Scala partition the global
name space and provide mechanisms for information hiding, similar to
Java packages. Values of class `Int` correspond to values of
Java's primitive type `int` (Scala makes no difference
between primitive and object types). More generally, all of Java's
primitive types have corresponding classes in the `scala` package.

We can reuse the automatically generated name `res0` to
refer to the computed value in subsequent expressions (this only works
in the REPL but not in a worksheet):

```scala
scala> res0 * res0
res1: Int = 9 
```

Java's ternary conditional operator `? :` has an equivalent in Scala,
which looks as follows:
```scala
scala> if (res1 > 10) res0 - 5 else res0 + 5
res2: Int = -2
```

In addition to the `? :` operator, Java also has if-then-else
statements. Scala, on the other hand, is a functional language and
makes no difference between expressions and statements: every
programming construct is an expression that evaluates to some
value. In particular, we can use if-then-else expressions where we
would normally use if-then-else statements in Java.
```scala
scala> if (res1 > 2) println("Large!") 
       else println("Not so large!")
res3: Unit = ()
```
In this case, the if-then-else expression evaluates to the value
`()`, which is of type `Unit`. This type indicates
that the sole purpose of evaluating the expression is the side effect
of the evaluation (here, printing a message on standard output). In
other words, in Scala, statements are expressions of type
`Unit`. Thus, the type `Unit` is similar to the
type `void` in Java, C, and C++ (which however, has no values). The value
`()` is the only value of type `Unit`. 

#### Names

We can use the `val` keyword to give a user-defined name to
a value, so that we can subsequently refer to it in other expressions:
```scala
scala> val x = 3
x: Int = 3
scala> x * x
res0: Int = 9
```
Note that Scala automatically infers that `x` has type
`Int`. Sometimes, automated type inference fails, in which
case you have to provide the type yourself. This can be done by
annotating the declared name with its type:
```scala
scala> val x: Int = 3
x: Int = 3 
```
A `val` is similar to a `final` variable in
Java or a `const` variable in JavaScript. That is, you cannot reassign it another value:
```scala
scala> x = 5
<console>>:8: error: reassignment to val
       x = 5
         ^
```
Scala also supports mutable variables, which can be
reassigned. These are declared with the `var` keyword
```scala
scala> var y = 5
y: Int = 5
scala> y = 3
y: Int = 3
```
The type of a variable is the type inferred from its initialization
expression. This type is fixed. Attempting to reassign a variable to a value of incompatible type results in a type error:
```scala
scala> y = "Hello"
<console>:8: error: type mismatch;
 found   : String("Hello")
 required: Int
       y = "Hello"
           ^
```

#### Functions

Here is how you write functions in Scala:

```scala
scala> def max(x: Int, y: Int): Int = {
         if (x > y) x
         else y
       }
max: (x: Int, y: Int)Int
```

Function definitions start with `def`, followed by the
function's name, in this case `max`. After the name comes a
comma separated list of parameters enclosed by parenthesis, here
`x` and `y`. Note that the types of parameters
must be provided explicitly since the Scala compiler does not infer
parameter types. The type annotation after the parameter list gives
the result type of the function. The result type is followed by the
equality symbol, indicating that the function returns a value, and the
body of the function which computes that value. The expression in the
body that defines the result value is enclosed in curly braces.

If the defined function is not recursive, as is the case for
`max`, the result type can be omitted because it is
automatically inferred by the compiler. However, it is often helpful
to provide the result type anyway to document the signature of the
function. Moreover, if the function body only consists of a single
expression or statement, the curly braces can be omitted. Thus, we
could alternatively write the function max like this:

```scala
scala> def max(x: Int, y: Int) = if (x > y) x else y
max: (x: Int, y: Int)Int
```

Once you have defined a function, you can call it using its name:
```scala
scala> max(6, 3)
res3: Int = 3
```

Naturally, you can use values and functions that are defined outside of a function's body in the function's body:
```scala
scala> val pi = 3.14159
pi: Double = 3.14159

scala> def circ(r: Double) = 2 * pi * r
circ: (r: Double)Double
```

You can also nest value and function definitions:
```scala
scala> def area(r: Double) = {
         val pi = 3.14159
         def square(x: Double) = x * x
         pi * square(r)
       }
area:(r: Double)Double
```

Recursive functions can be written as expected. For example, the
following function `fac` computes the factorial numbers:
```scala
scala> def fac(n: Int): Int = if (n <= 0) 1 else n*fac(n-1)
fac: (n: Int)Int

scala> fac(5)
res4: Int = 120
```

#### Scopes

Scala's scoping rules are similar to Java's:

```scala
val a = 5
// only a in scope
{
  val b = 4
  // b and a in scope

  def f(x: Int) = {
    // f, x, b, and a in scope
    a * x + b 
  }
  // f, b, and a in scope
}
// only a in scope
```

There are some differences to Java, though. Scala allows you to redefine
names in nested scopes, even if that name has already been bound in
an outer local scope:
```scala
val a = 3;
{
  val a = 4 // hides outer definition of a
  a + a     // yields 8
}
```
However, as in Java, you cannot redefine a name in the same scope:
```scala
  val a = 3
  val a = 4 // does not compile
```
Also, unlike in Java, you can't refer to a name before it is bound in
the same block, even if that name has been bound in an outer scope:

```scala
{
  val x = 2;
  {
    println(x) // Forward reference to `x` declared in this  block. Does not compile
    val x = 3;
    x + x
  }
}
```

