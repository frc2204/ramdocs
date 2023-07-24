# Variables

## Expression

Expressions simply describe any computation that produces a value and are the basic building blocks of any program.

!!! example "Examples of expressions"
    You've probably seen expressions before. Here are some examples:
    $$
    \large
    22 + 4, \frac{22}{4}, \sin \pi, \sum_{i=1}^n{i}, -2204, \log x, 20.24
    $$

### Call Expressions

Let's take a look at the expression `add(2, 3)`. This is called a **call expression**. It is composed of the following parts:

- `add`: the **function name**, known as the **operator**
- `2` and `3`: the **operands**


When we evaluate a call expression, we 

1. Evaluate the operands from left to right
2. Apply the operator (function) to the operands (arguments)

![Call Expression](https://cdn.discordapp.com/attachments/786053009964269591/1132926958821462036/image.png)

??? question "Practice: Evaluate `add(2, add(3, 4))`"
    Let's walk through step-by-step how we would evaluate this expression.

    ```mermaid
    stateDiagram
        state "add(2, add(3, 4))" as [original]
        state "evaluate 2" as [2]
        state "evaluate add(3, 4)" as [a34]
        state "evaluate 3" as [3]
        state "evaluate 4" as [4]
        state "apply 3 + 4" as [ap34]
        state "7" as [7]
        state "apply 2 + 7" as [ap27]
        state "9" as [9]
        [*] --> [original]
        [original] --> [2]
        [original] --> [a34]
        [a34] --> [3]
        [a34] --> [4]
        [3] --> [ap34]
        [4] --> [ap34]
        [ap34] --> [7]
        [2] --> [ap27]
        [7] --> [ap27]
        [ap27] --> [9]
        [9] --> [*]
    ```

    Keep in mind this whole time, we are evaluating each operand from left to right. Once we encounter another call expression, we begin the call expression evaluation for the specific call expression. Finally we apply the operator to the operands.

### String Templates
It's useful to know how to print the contents of variables to standard output. You can do this with string templates `$`, which gives access data stored in variables and other objects, and convert them into strings. 

!!! info
    A string value is a sequence of characters in double quotes `""`. This can include words, sentences, and even whole paragraphs. 
    
```kotlin
fun main() {
    val customers = 10
    println("There are $customers customers")
    // There are 10 customers

    println("There are ${customers + 1} customers")
    // There are 11 customers
}
```

## Assignment Statements
All programs need to be able to store data, and variables help you to do just that. In Kotlin, you can declare:

- read-only variables with `val`
- mutable variables with `var`

When you declare a variable, you assign it an **expression** with the `=` operator. This is called an assignment statement.

!!! example "Example of `val`"
    We can declare a read-only variable `x` with the value `22`, and a read-only variable `y` with the value `4`.
    === "Kotlin"
        ```kotlin
        fun main() {
            val x = 22
            val y = 4
            println(x + y)
        }
        ```
    === "Java"
        ```java
        public class Main {
            public static void main(String[] args) {
                int x = 22;
                int y = 4;
                System.out.println(x + y);
            }
        }
        ```

!!! example "Example of `var`"
    Let's say my bank account has `$100` in it. I can declare a mutable variable `bankAccount` with the initial value of `100`.
    === "Kotlin"
        ```kotlin
        fun main() {
            var bankAccount = 100
            println("My bank account has:")
            println(bankAccount)

            bankAccount = 80;
            println("Just spent $20, I now have $bankAccount left")
        }
        ```
    === "Java"
        ```java
        public class Main {
            public static void main(String[] args) {
                int bankAccount = 100;
                System.out.println("My bank account has:");
                System.out.println(bankAccount);

                bankAccount = 80;
                System.out.println("Just spent $20, I now have $" + bankAccount + " left");
            }
        }
        ```

!!! question "Why not declare everything as a `var`?"
    Is it alright to legal everything as a `var`? Yes! No ones stopping you :wink:

    However, it is considered good practice to declare variables as `val` by default, and only declare variables as `var` if necessary. Declaring variables properly can not only let other people know how you intend to use the variable, but also help the compiler optimize your code and catch any potential bugs.

## String Templates
It's useful to know how to print the contents of variables to standard output. You can do this with string templates `$`, which gives access data stored in variables and other objects, and convert them into strings.

!!! info
    A string value is a sequence of characters in double quotes `""`. This can include words, sentences, and even whole paragraphs. See more about Strings [here](#basic-data-types)

```kotlin
fun main() {
//sampleStart
    val customers = 10
    println("There are $customers customers")
    // There are 10 customers

    println("There are ${customers + 1} customers")
    // There are 11 customers
//sampleEnd
}
```

### Practice
Complete the code to make the program print "Mary is 20 years old" by using the information provided in the variables `name` and `age`.

```kotlin
fun main() {
    val name = "Mary"
    val age = 20
    // Write your code here
}
```
??? tip "Stuck? Here's a hint"
    Think about how you can use [string templates](#string-templates) to print the contents of variables to standard output.

??? success "Solution"
    The solution uses [string templates](#string-templates) to get the values of `name` and `age` and combine them into the expected format.
    ```kotlin
    fun main() {
        val name = "Mary"
        val age = 20
        println("$name is $age years old")
    }
    ```

