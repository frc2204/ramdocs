# Collections

## Collection & Iterable Interface

Collections store a number of objects of the same type. The objects within a collection are often referred to as **elements**
or **items**. For example, all students within a school form a collection that can be used to calculate their average grades.
In this case, each student can be represented as an individual **object**, or **element** inside the collection.

Before we go into the different collection types in Kotlin, it is important for us to understand the *iterable interface*
and how it relates to Collections.

[**Interfaces*](https://kotlinlang.org/docs/interfaces.html): Interfaces in kotlin contain abstract methods and method implementations for their implementing classes.

`Iterable interface` defines the operations for iterating over elements. Let's go back to our previous example of students 
inside a school being a "collection". If we want to go through this "collection" and obtain information about every students'
names, how would we approach that? In the real world, we can set the students up in a line and record their names one by one.
And with collections in kotlin, we can approach that with specific methods that we **inherit** from the iterable interface
that allow us to iterate or loop through a collection. The Collection interface also has its own helpful implementations of methods for its 
subclasses as well. Such as getting the size, checking item membership, checking if two collections are equal, and so on.

**Overview:** *Collection <T>* is the root of the collection hierarchy. The collection interface **implements** the Iterable interface,
meaning that it is a child of the iterable interface and will be **inheriting** many methods and properties from its parent.

## List

A ***List*** is an ordered collection with access to elements by indices – integer numbers that reflect their position. 
Elements can occur more than once in a list. An example of a list is a telephone number: it's a group of digits, their 
order is important, and they can repeat.

Similar to languages like Java & C++, Kotlin indices to access elements also begin at `0`. 

!!! example "Example of *`Accessing List Elements Using Indices`*"
    We can access the elements within a List by using the index operator `[]`. By passing
    in the index value that we wish to access `[0]`, we can get the element inside.
    === "Kotlin"
        ```kotlin
        fun main() {
        //sampleStart
            val myList = listOf<Int>(1, 2, 3, 4, 5)
            println(myList[0])
        //sampleEnd
        }
        ```
    === "Java"
        ```java
        public class Java {
            public static void main(String[] args) {

                List<Integer> myList = new ArrayList<>();

                myList.add(0, 1);

                System.out.println(myList.get(0));
            }
        }
        ```

`Explanation:` Inside our simple program, we initialized a *readable* list of integers (only able to store integer values) 
               with the values 1, 2, 3, 4, and 5. We then made an output to the console with the value stored in index ([])
               0. If we were to access the index [1], the value returned would be 2.

`When we think about lists:` It can be helpful for us to visualize list elements as independent boxes, and each box contains
                            a value. From our previous example, we can think of the readable list *myList* as a container
                            for the boxes. And the independent boxes store values of 1, 2, 3, 4, and 5. When we outputted 
                            index 0 ([0]), we are essentially saying: "open the box at index 0 and tell me the value inside."

`List of Strings`: We can also create a list of strings:

!!! example "Example of *`List of Strings`*"
    We can create a list of Strings in Kotlin similar to a list of Integers that we've seen previously.
    === "Kotlin"
        ```kotlin
        fun main() {
            //sampleStart
            val myStringList = listOf<String>("f", "u", "n", "n", "y")
            print(myStringList[0] + myStringList[1] + myStringList[2] + myStringList[3] + myStringList[4])
            println()
            for(i in myStringList) {
                print(i)
            }
        //sampleEnd
        }
        ```
`Explanation:` Inside our example, we created a new list of type *String* and initialized it with individual characters
               that make up the word "funny". We also used a *for loop* to help us print out the individual characters 
               instead of printing them out individually using a print statement. It is helpful right now to be exposed to the ideas
               of a *for loop*, and we will be covering them in later chapters.

**`Lists`**: After exploring many examples, we can say that *lists* are needed when we need to store multiple values of the same
             type. *Lists* are also helpful when we need to store values whose order matters, just like our 
             list of strings example.

### Read-only List

**Similarities:** Bringing back val vs. var from previous chapters, a readable-only list is quite similar to a *val* variable, where once
it is initialized, the value of it can not be changed. This means that once we initialized a list with values, we are 
not allowed to update the values(nor size), and certain operations will be limited.

Consider the following code:
=== "Kotlin"

```kotlin
fun main() {
    //sampleStart
    val list = listOf<Int>(1, 2, 3, 4, 5)
    list.add(6) // not legal
    list.remove(0) // not legal
    //sampleEnd
}
```

`Explanation:` Why is the add & remove methods illegal? That is because a list is automatically read-only when we 
               initialize them, meaning that the contents & size **can not** be updated after the initialization.

`Rules:` When we choose to use a fixed list, we should know that..

1. After the initialization, the size is **not** mutable
2. After the initialization, we **can not** add elements into the list
3. After the initialization, we **can not** remove elements from the list

*`why immutable lists?:`* We use immutable lists when we are working with fixed elements. An example can be country
                          names. Another example can be individual phone number digits, where their orders matter,
                          and can not be changed. In general, it is a good programming practice to use immutable lists when we can
                          or need to.

### Mutable List

**Similarities:** Referring back to our knowledge about var and val from previous chapters, a mutable list is quite similar
                  to a var variable, where it can be changed in different places throughout our code. 

*For example:*

=== "Kotlin"
    ```kotlin
    fun main() {
    //sampleStart
    // initial size is 4 (counting from 0)
    val myMutableList = mutableListOf<Int>(1, 2, 3, 4, 5)
    // size is now 5
    myMutableList.add(6)
    // size is now 4
    myMutableList.removeAt(0)
    for(i in myMutableList) {
    print("$i")
    }
    //sampleEnd
    }
    ```
`Explanation:` Inside our program, we initialized a new integer mutable list with the values 1, 2, 3, 4, and 5.
               Since mutable lists are *dynamic*, meaning that the size would adjust according to its elements, we
               are able to add and remove elements. Inside the code, the `add()` method is used to add a new element
               into our list. We then used the `removeAt()` method to remove the element stored in index 0, which is 1.

*`why mutable lists?:`* We use mutable lists when we are working with unknown amount of values. For example, 
                        we may prefer a mutable instead of a immutable when we are working with a list that contains
                        a persons' favorite music - this list will constantly be changed and updated and some songs
                        will be removed and more will be added in.

### List Methods

???+ tip "`get()`"
    !!! example "The get() method requires an argument of a valid index number, and returns the value inside the index"
        === "Kotlin"
        ```kotlin
            fun main() {
            val myList = listOf<Int>(1, 2, 3)
            println("Value at index 2 is: ${myList.get(2)}")
        }
        ```

???+ tip "`subList()`"
    !!! example "The subList() method requires two arguments, first is begin index (inclusive), second is end index(exclusive)"
        === "Kotlin"
        ```kotlin
            fun main() {
            val myList = listOf<Int>(1, 2, 3, 4, 5)
            println("Value between index 0 to 3 is: ${myList.subList(0, 3)}")
        }
        ```

???+ tip "`add()`"
    !!! example "The add() method requires one argument, and it is the value that we wish to add to our current mutable list. The value will automatically be placed behind all indexes"   
        === "Kotlin"
        ```kotlin
            fun main() {
            val myList = mutableListOf<Int>(1, 2, 3)
            myList.add(4)
            myList.add(5)
            print(myList)
        }
        ```

???+ tip "`remove()`"
    !!! example "The removeAt() method removes the element at the given index"
        === "Kotlin"
        ```kotlin
            fun main() {
            val myList = mutableListOf<String>("Hello", "World", "And", "Yes")
            println(myList)
            myList.removeAt(3)
            println(myList)
            myList.removeAt(2)
            println(myList)
        }
        ```

???+ tip "`equals()`"
    !!! example "The equals() method takes in another list of the same type, and returns a boolean on whether the two lists are equal"
        === "Kotlin"
        ```kotlin
            fun main() {
            val myListA = listOf<Int>(1, 2, 3, 4)
            val myListB = listOf<Int>(1, 2, 3, 4)
            val myListC = listOf<Int>(1, 3, 2, 5)
            println(myListA.equals(myListB))
            print(myListB.equals(myListC))
        }
        ```
## Set

A `Set` stores unique elements; their order is generally undefined. null elements are unique as well: a Set can contain 
only one null. Two sets are equal if they have the same size, and for each element of a set there is an equal element 
in the other set.

**Unlike lists**: the orders in a set do not matter, and when we are using a set, we *don't* care about the orders. 
As well, sets don't support indices to access specific indexes like lists.

!!! example "Example of a set"
    === "Kotlin"
    ```kotlin
    fun main() {
    //sampleStart
    val mySet = setOf(4, 2, 1, 3, 5, 9)
    // not legal: print(mySet[0])
    print(mySet)
    //sampleEnd
    }
    ```

*`Explanation:`* A set can also be seen as an *unordered list*, and the action mySet[] is not legal

### Read-only Set

`Immutable Set:` A read-only set is very similar to a read-only list, where no new elements can be added or removed

### Mutable Set

`Mutable Set:` A mutable set is also very similar to a mutable list, where elements could be added and removed. However,
               a duplicate element can be added.

### Set Methods

???+ tip "`add()`"
    !!! example "The add() method takes in one integer argument and adds the integer to the end of the set"
        === "Kotlin"
        ```kotlin
        fun main() {
            val mySet = mutableSetOf<Int>(4, 2, 5, 6, 1)
            mySet.add(4)
            mySet.add(5)
            mySet.add(7)
            // notice how the elements 4 and 5 will not printed out for the second time -> they were never added
            print(mySet)
        }
        ```

???+ tip "`remove()`"
    !!! example "The remove() method takes in one integer argument and removes that integer from the list (if not in list, does nothing)"
        === "Kotlin"
        ```kotlin
        fun main() {
            val mySet = mutableSetOf<Int>(4, 2, 5, 6, 1)
            mySet.add(7)
            // does nothing as 9 does not exist in our set
            mySet.remove(9)
            // removes the integer 5 and shifts everything "forward"
            mySet.remove(5)
            print(mySet)
        }
        ```



## Map

`Map<K, V>` is not an inheritor of the Collection interface; however, it's a Kotlin collection type as well. A Map 
stores key-value pairs (or entries); keys are unique, but different keys can be paired with equal values. The Map 
interface provides specific functions, such as access to value by key, searching keys and values, and so on.

!!! example "Key to Value with `Maps`"
    === "Kotlin"
    ```kotlin
    fun main() {
        // initializing a map that maps a integer key to a string value
        val myMap = mapOf<Int, String>(1 to "one", 2 to "two", 3 to "three")
        print(myMap)
    }      
    ```

`Explanation:` Notice how when we created our map, we explicitly referenced it is a map of Integer keys ot String values,
               this is *not* required, but is a good practice. When we initialized the map, we also *put* some pairs inside the map.
               In simple words, the *to* keyword pairs the key to the value in our map. So the operation *1 to "one"* means
               to make a new key with integer number 1, and have it store the string of "one". And thus in the future,
               it provides simple access to look-up the values stored inside 1.

`Why Maps?:` Maps allow us to establish relationships between keys and values, and allow us to retrieve data quickly.
             Since every key is unique in a map, it allows us to more accurately retrieve the data we need. An example
             key-value relationship can be student to grade. Since every student is different (unique keys), we can map
             them to their corresponding grade. And thus in the future, it provides easier access for us to quickly look 
             at a student's grades.

### Read-only Map

`Read-only maps:` Similar to immutable sets and lists, we will not be able to add, remove, or change any contents
                  within the immutable map after it is initialized. 

!!! example "Immutable Map"
    === "Kotlin"
    ```kotlin
    fun main() {
        val myImmutableMap = mapOf<Int, Char>(1 to 'a', 2 to 'b', 3 to 'c', 4 to 'd')
        // not legal
        //myImmutableMap.put(5, 'e')
        // not legal
        //myImmutableMap[1] = 'f'
        print(myImmutableMap)
    }
    ```

`Explanation: ` As shown above, operations that attempts to edit a map after its declaration is *illegal*.
                (you can remove the comments and see the output!)

### Mutable Map

`Mutable Maps:` Mutable maps functions exactly the same as an immutable map, other than the abilities to be able
                to add, remove, and change the contents after its declaration. Consider the following code:

!!! example "Mutable Maps"
    === "Kotlin"
    ```kotlin
    fun main() {
    val myMutableMap = mutableMapOf<Int, Char>()
    // assignment operator for maps
    myMutableMap[1] = 'a'
    // can also use put() -> works in java
    myMutableMap.put(2, 'b')
    // adding more keys-values
    myMutableMap[3] = 'c'
    myMutableMap[4] = 'd'
    // creating a new pair with the key of 1 with a different value -> watch what happens
    myMutableMap[1] = 'f'
    print(myMutableMap)
    }
    ```

`Explanation:` As we can see, a mutable map's contents can be added or edited. However, if we make a new key that already
               exists in our map, the new key will overwrite the old key with the new value.
               The [] operator is different for maps than for lists and arrays. The `[]` here is used to create 
               a new key and store the value on the right side of the equal sign. We are basically saying: "Put whatever value
               is on the right side of the equal sign, and store it into the key on the left side.

### Map Methods

???+ tip "`keys()`"
    !!! example "The keys() method returns a list of keys from the map"
        === "Kotlin"
        ```kotlin
        fun main() {
            //sampleStart
            val myMap = mapOf<Int, Char>(1 to 'a', 2 to 'b', 3 to 'c')
            print(myMap.keys)
            //sampleEnd
        }
        ```


