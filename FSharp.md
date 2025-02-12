<!-- title: F# Cheat Sheet -->
# F# Cheat Sheet

- [F# Cheat Sheet](#f-cheat-sheet)
  - [Introduction](#introduction)
  - [Current Link](#current-link)
  - [Functions](#functions)
    - [Basics](#basics)
      - [Basic Commads for every programm](#basic-commads-for-every-programm)
      - [Strings](#strings)
        - [Verbatim String](#verbatim-string)
        - [Triple Qoutes String](#triple-qoutes-string)
        - [String Concatenation](#string-concatenation)
      - [Mutables](#mutables)
      - [Function Definition](#function-definition)
      - [List Definition](#list-definition)
      - [Array Definition](#array-definition)
    - [Operators](#operators)
      - [Basic operators](#basic-operators)
        - [Equal \& Not Equal](#equal--not-equal)
        - [Char from string](#char-from-string)
        - [Range from string](#range-from-string)
      - [Pipe](#pipe)
      - [Composition](#composition)
    - [Print escapes](#print-escapes)
      - [Baisc Types](#baisc-types)
      - [Lists \& Arrays](#lists--arrays)
      - [Special Characters](#special-characters)
      - [Padding](#padding)
    - [List Functions](#list-functions)
      - [Map](#map)
      - [Filter](#filter)
    - [String functions](#string-functions)
      - [Collect](#collect)
      - [Forall](#forall)
      - [Exits](#exits)
      - [Init](#init)
      - [Iter](#iter)
    - [Char functions](#char-functions)
      - [IsDigit](#isdigit)
      - [IsUpper](#isupper)
    - [Math functions](#math-functions)
      - [Basics](#basics-1)
        - [Addition \& Subtraction](#addition--subtraction)
        - [Division \& Multiplication](#division--multiplication)
        - [Exponential \& Square Root](#exponential--square-root)
        - [Rounding](#rounding)
        - [Logarithmic](#logarithmic)
        - [Absolute Values](#absolute-values)
      - [Advanced Math Functions](#advanced-math-functions)


## Introduction
This is a short overview over all of the F# commands that we have learned during our learning process.

## Current Link
https://youtu.be/c7eNDJN758U?t=2046

## Functions

### Basics

These are the basic functions and definitions we need to make the programm run.

**Remeber Variables are defined in Lower Snake Case**

```fs
let this_is_the_way 
``` 

#### Basic Commads for every programm

```fs
// function or variable definition
let

// recursive function definition
let rec

// mutable variable
let mutable

// print new line 
printfn "" 

// print inline
printf 

// import system for reading console input
open System

// get key input from user
Console.ReadKey()

// get console line input from user
Console.ReadLine()

// lambda expression remeber fun
(fun x -> x * 2)

// GetType Expression
let x = 10
printfn "TypeOf %A" (x.GetType())

// exit programm
exit 100
```

####  Strings

##### Verbatim String
```fs
let varbatim_string = @"This ignores backslashes"
```
##### Triple Qoutes String
```fs
let triple_string = """This ignores backslashes and double "quotes" """
```
##### String Concatenation
Use `+` to concatenate strings

```fs
let strings = "test" + "test2"
```

#### Mutables
Mutables are not commonly used in f# but this is how.

```fs
// mutable variable
let mutable weight = 90

// change mutable variable  
weight <- 85

// other approach
let change_me ref 10
change_me := 50

// in order to print this we have to use a ! in the print statement
printfn "Print change_me %i" ! change_me
```

#### Function Definition
```fs
//  func name | paramenter | return type | function value
let double = (x : int) : int = x + x
``` 

#### List Definition 
A list is an immutable collection of elements of the same type. Implemented internally as a linked list.

***Not with comma!***
```fs
let new_list = [1;2;3;4]
``` 
####  Array Definition
Arrays are fixed-size, zero-based, collections of consecutive data elements maintained as one block of memory. They are mutable; individual elements can be changed.

### Operators


#### Basic operators
##### Equal & Not Equal
```fs
let equal = 1 = 1 // true
let not_equal = 1 <> 2 // true
```

##### Char from string
Get a single char from string using `.[x]`

```fs
let char1 = "Test1234".[0] // T
```
##### Range from string
Get a range of chars from string using `.[x..y]`

```fs
let char1 = "Test1234".[0..3] // Test
```

#### Pipe

Pipe operator `|>` is used to chain functions and arguments together.

    let addTwoSubtractTwoNegateAndPrint num =
        num |> add 2 |> subtract 2 |> negate |> print



#### Composition 
Composition operator `>>` is used to compose functions:
```fs
    let addTwoSubtractTwoNegateAndPrint' = 
    add 2 >> subtract 2 >> negate >> print
```


Caution: The output is the _last_ argument to the next function.
```fs
    // `addTwoSubtractTwoNegateAndPrint 10` becomes:
    10
    |> add 2       //  2 + 10  = 12
    |> subtract 2  //  2 - 12  = -10
    |> negate      // -1 * -10 = 10
    |> print       // "The number is 10"
```

### Print escapes

Print escapes are used in the string while printing to the console.

#### Baisc Types
```fsharp
printfn "This prints a string: %s" "string"

printfn "This prints an integer %i" 1

printfn "This prints a float %f" 1.0

printfn "This prints a float %b" false

printfn "This prints a float with more values %M" 120.123123142134213M

printfn "This prints a char %c" "test".[1] 
// or 
printfn "This prints a char %c" 'e'

``` 

#### Lists & Arrays

```fs
printfn "This prints a List: %A" [1;2;3;4;5;6]
```

#### Special Characters
You need to escape `%` and `*` individually in a string by doubling the char.
```fs
let percent_string = "5 %% 5 = 1"
let mul_string = "5 ** 5 = 25"
```


#### Padding

```fs
printfn "This adds padding to the left %-5i" 1
printfn "This adds padding to the right %5i" 1
printfn "This adds padding to both sides %-5i %5i" 1
printfn "This adds dynamic padding  %*s" 1 "test"
```
### List Functions

#### Map
Map changes every element of a list.

```fs
let list = [1;2;3;4]
let doubled = list.map(fun x -> x * 2)
```

#### Filter
Filter takes only those elemets of a list that fit the filter criteria.

```fs
let list = [1;2;3;4]
let even_elements = list |> List.filter(fun x -> x % 2 = 0)
```

### String functions

#### Collect
Collect iterates over all character and does something with them.
```fs
// adds a comma afer every letter
let commas = String.collect (fun x -> sprintf("%c, ") x) "commas"
```

#### Forall
For all checks if the given requirement is met by all characters in a string.

```fs
let is_upper = "TEST" |> String.forall(fun x -> Char.IsUpper x) // true
```

#### Exits 
Tests if any character of the string satisfies the given predicate.
```fs
let exists = String.exists(fun x -> Char.IsUpper(x)) "Test1234" 
printfn "%b" exists
```

#### Init
Init creates a new string with the length of x.
```fs
let new_string = String.init 10 (fun x -> x.ToString()) 
printfn "%s" new_string
```

#### Iter
String iter does a function for each character in a string. Kinda loke a for each in dart.
```fs
String.iter (fun c -> printfn "%c" c) "Print Me" 
``` 


### Char functions

#### IsDigit
Checks if a char is a digit.
```fs
Char.IsDigit()
```
#### IsUpper
Checks if a char is upper case.
```fs
Char.IsUpper()
```
### Math functions 

####  Basics

##### Addition & Subtraction
```fs
let add = 1 + 1 
let sub = 2 - 1
```

##### Division & Multiplication
```fs
let mul = 2 * 2 
let div = 1 / 4
```

##### Exponential & Square Root
To calculate an integer to the power of x you use the operator `**`
```fs
let power_of_two = 2 ** 2 // 4 
```

To calculate the Square root use `sqrt(x)`
```fs
sqrt(25.0) // -> float
```
##### Rounding
```fs
// round up
floor(4.5) // -> float

// round down
ceil(4.5) // -> float
```
##### Logarithmic

```fs
log 2.2 // -> float
log10 1000 // -> float
```

##### Absolute Values

```fs
abs(-1) // -> int
```


#### Advanced Math Functions



