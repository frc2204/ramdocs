# Introduction to Kotlin

Kotlin is a programming language that is designed to be concise, safe, and expressive. It is runs on multiple platforms, including JVM, Android, browsers, and even natively on computers!

![Kotlin](https://kotlinlang.org/docs/images/kotlin-logo.png)

## Why Kotlin?
In the past, our team has used Java as our primary programming language. However, we have decided to switch to Kotlin. Here's why:

- **Conciseness**, **multi-paradigm structure** and **interoperability**
- As a first programming language, gradual introduction of programming concepts **without confusing boilerplate**
- Learn **modern, generalizable programming habits** which can be applied to **use in the industry**

### Kotlin in Industry and Academia
Kotlin has already established itself to be highly impactful in sectors  including mobile development, and server-side & cloud development. Additionally, Kotlin is trending in fields such as Multiplatform development, web frontend development, data science & machine learning, and desktop application development.

<div class="grid" markdown>

-   :fontawesome-solid-graduation-cap: __Academically Recognized__

    Top universities such as Stanford, Cambridge, UPenn, UMich, John Hopkins, and UCLA have adopted Kotlin within their computer science programs.

    [:octicons-arrow-right-24: See which Universities teach Kotlin](https://kotlinlang.org/education/courses.html)

-   :fontawesome-solid-industry: __Language of the industry__

    Kotlin is used by top companies such as :simple-google: Google, :simple-amazon: Amazon, :simple-twitter: Twitter, :simple-reddit: Reddit, :simple-netflix: Netflix, :simple-uber: Uber, :simple-slack: Slack, just to name a few.

</div>

## Features

### Concise Code
Compared to Java, an industry standard, Kotlin is much more concise - reducing the number of lines of code by 40% on average. This, paired with a simple syntax, allows us to focus on the actual ideas behind our code and programming.

### Multi-Platform
Kotlin is a multi-platform language, meaning that code can be run or executed across multiple platforms. Essentially, this allows us to write code once, and run it anywhere.

???+ question "How does Kotlin run on multiple platforms?"
    Kotlin is a compiled language, meaning that it is translated (compiled) into bytecode (a set of instructions that can be executed by a computer). Then, bytecode can be translated into specific machine code for a specific platform.

    #### Compilation Processes
    A more traditional approach would be to compile the code into machine code for a specific platform, which is what the C programming language does.

    ```mermaid
    graph LR
        S[Source Code]
        M[Machine Code]
        C[Computer]

        S -- Compiler --> M -- Runs On --> C
    ```

    The problem with this approach is that we need to compile the code for each platform that we want to run it on. This means that we need to compile separate versions of the code for each platform, such as Windows, MacOS, and Linux.

    #### The Java Virtual Machine

    What if we could compile the code once, and run it anywhere? This is where the Java Virtual Machine (JVM) comes in. JVM handles the translation of bytecode into machine code for a specific platform.

    ```mermaid
    graph LR
        S[Source Code]
        B[Bytecode]
        M[JVM]
        
        subgraph P[JVM Platforms]
            Android
            Windows
            MacOS
            Linux
        end

        S -- Compiler --> B -- Run the Program --> M -- Runs Anywhere --> P
        S -. Runs Once .-> B
    ```

    #### Kotlin Multiplatform
    Kotlin takes this idea one step further, allowing us to run code on multiple platforms, including JVM

    ```mermaid
    graph LR
        S[Source Code]
        B[Bytecode]
        M[JVM]
        W[Web Assembly]
        Br[Browser]
        I[iOS]
        
        subgraph P[JVM Platforms]
            Android
            Windows
            MacOS
            Linux
        end

        K[Native Code] 

        S -- Compiler --> B -- Run the Program --> M -- Runs Anywhere --> P
        S -- Compiles --> W --> Br
        S -- Compiles --> K --> P
        K --> I
    ```

### Static Typing
Static typing is a way of defining the data types of variables and expressions in a programming language, enforcing the type of operations that can be performed on data. 

#### What is Typing?
Why does this typing matter though? Let's break this down into a couple of exercises. Think of what result you would get if you were to perform the following operations:

??? success "Adding two words, `John` + `Doe` = `???`"
    If we were to add two words, `John` and `Doe`, we would get `JohnDoe`. This is because the `+` operator for words will concatenate them together.
    
    If your answer was `John Doe`, you would be wrong. That would be the result if we were to add `John` and `Doe` with a space in between them. Don't worry about that though :hugging:

??? success "Adding two numbers, `14` + `3` = `???`"
    If we were to add two numbers, `14` and `3`, we would get `17`. This is because the `+` operator is defined for numbers, and multiplies them together. Makes sense, right?

??? failure "What about two **words**, `1` + `1` = `???`"
    If we were to add two words, `1` and `1`, we would get `11`. This is because the `+` operator is defined for words, and concatenates them together. 

    If you answered `2`, you would be wrong. Remember, when you add two words together, you need to *literally add them together*. Beginning to see a problem? :thinking:

As shown in the examples above, static typing allows us to define the type of operations that can be performed on data. 
In this case, adding two words will concatenate them together, while adding two numbers will mathematically add them together.

In other words, the operation performed on data is dependent on the type of data. This is the core idea behind any typing.

#### Enforcing Type Safety
Static typing also allows us to enforce types - meaning that the type of element must remain a specific type at any given time. This means that we can prevent operations from being performed on data that is not defined for that type.

For example, if we were to try to add a word with a number, we would get an error. This is because the `+` operator is not defined for words and numbers.

!!! note
    Static typing is not the only way to define the type of operations that can be performed on data. There are other ways, such as dynamic typing, which is used in languages such as Python and JavaScript.

#### Type Inference
Type inference is a way of automatically determining the type of a variable or expression. This allows us to write code without having to explicitly define the type of a variable or expression - it saves us time and makes our code more concise.

For example, if we were to define a variable `name` and assign it the value `"John"`, we would not have to explicitly define the type of `name` as a word. Instead, Kotlin would automatically infer that `name` is a word. Note that typing still exists, and add operations on `name` would still result in concatenation.

#### Null Safety
Kotlin enforces null safety, meaning that we cannot assign a variable to `null` unless we explicitly define it as it being nullable. This prevents us from encountering null pointer exceptions, an extremely common error in Java.

## Hello World

Your turn! Let's write our first Kotlin program.
!!! tip
    While you can write Kotlin code on the web, it is recommended that you eventually properly setup your computer for Kotlin development, allowing you to write and run Kotlin code locally.

    For the sake of simplicity for now, we can embedded Kotlin code in this website or [Kotlin Playground](https://play.kotlinlang.org) . You can run the code with the ![Run](https://resources.jetbrains.com/help/img/idea/2023.1/app.actions.execute.svg) on the top right corner.

```kotlin
fun main() {
    println("Hello World!")
    // Hello World!
}
```

This is a simple program that prints `Hello World!` to the console. Let's break it down.

- `fun` is used to declare a function.
- The `main` function is where your program starts from - it's the entry point to the program.
- The body of a function is written between curly braces `{}`.
- `println` is a function that prints a line to the console.

!!! info
    Functions are discussed in more detail in a couple of sections. Until then, all examples use the `main()` function.

