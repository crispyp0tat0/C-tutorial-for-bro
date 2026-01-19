# C-tutorial-for-bro

# Preface

This document is a **modified derivative** of the *GNU C Reference Manual*. It is intended as a reference and instructional manual for the C programming language **as implemented by the GNU Compiler Collection (GCC)**, with additional clarification and reorganization for practical learning purposes.

Specifically, this manual documents:

* The 1989 ANSI C standard, commonly known as **C89**, as the baseline language
* Selected features of the 1990 ISO C standard (**C99**), to the extent that they are implemented by GCC
The current state of **GNU extensions** to standard C

C89 is treated as the baseline throughout this manual. C99 features and GNU-specific extensions are **explicitly labeled** as such. Where behavior is implementation-defined, unspecified, or undefined, this is stated explicitly.

This manual is **not an official GNU document**. It does not claim to reflect current or future GCC policy. Statements regarding language features and compiler behavior describe the implementation as documented in the original GNU C Reference Manual and are adapted for explanatory clarity.

The C language includes a set of preprocessor directives used for macro replacement, conditional compilation, and file inclusion. While preprocessing is commonly described in C language manuals, the GNU C preprocessor is documented separately in *The C Preprocessor**, which covers preprocessing for C, C++, and Objective-C. As in the original manual, preprocessing is not described in detail here.

This manual was **originally adapted for a specific friend (“bro”)** as a learning and reference aid. While written with that context in mind, the technical content is intended to remain precise, standards-aware, and suitable for general reference.

## Credits

### Original Work

This document is based on the *GNU C Reference Manual*, distributed under the **GNU Free Documentation License (GFDL)**.

The following credits are preserved from the original work. These individuals contributed to the GNU C Reference Manual through editing, proofreading, ideas, typesetting, and administrivia:

Diego Andres Alvarez Marin, Nelson H. F. Beebe, Karl Berry, Robert Chassell, Hanfeng Chen, Mark de Volld, Antonio Diaz Diaz, dine, Andreas Foerster, Denver Gingerich, Lisa Goldstein, Robert Hansen, Jean-Christophe Helary, Mogens Hetsholm, Teddy Hogeborn, Joe Humphries, J. Wren Hunt, Dutch Ingraham, Adam Johansen, Vladimir Kadlec, Benjamin Kagia, Dright Kayorent, Sugun Kedambadi, Felix Lee, Bjorn Liencres, Steve Morningthunder, Aljosha Papsch, Matthew Plant, Jonathan Sisti, Richard Stallman, J. Otto Tennant, Ole Tetlie, Keith Thompson, T.F. Torrey, James Youngman, and Steve Zachar.

In the original GNU C Reference Manual, **Trevis Rothwell** served as project maintainer and, along with **James Youngman**, wrote the bulk of the text.

Some example programs in the original manual are based on algorithms from *The Art of Computer Programming* by **Donald Knuth**.

### Modifications

This version has been **modified, reorganized, and extended** from the original GNU C Reference Manual. Changes include restructuring, additional explanations, clarifications, and pedagogical adjustments.

These modifications were made by the current maintainer of this repository. Responsibility for any errors or omissions introduced by these changes lies solely with the modifier and not with the original GNU authors or contributors.

## Note (not part of the specification):

If you are here to nitpick wording, policy, or historical accuracy, you probably should have gone straight to the original *GNU C Reference Manual*.

This version exists because *bro* wanted a modified one.

If you are not bro, your complaints are politely acknowledged and equally politely ignored.

# Lexical Elements

This chapter describes the lexical elements that make up C source code after preprocessing. These elements are called tokens. There are five types of tokens: keywords, identifiers, constants, operators, and separators. White space, sometimes required to separate tokens, is also described in this chapter.

* [Identifiers](#identifiers)
* [Keywords](#keywords)
* [Constants](#constants)
* [Operators](#operators)
* [Separators](#separators)
* [White Space](#white-space)

## Identifiers

Identifiers are sequences of characters used for naming variables, functions, new data types, and preprocessor macros. You can include letters, decimal digits, and the underscore character `_` in identifiers.

**IMPORTANT: The first character of an identifier cannot be a digit.**

Lowercase letters and uppercase letters are distinct, such that foo and FOO are two different identifiers.

When using GNU extensions, you can also include the dollar sign character ‘$’ in identifiers.

e.g.:

```C
// Correct
foo_bar_BAZ_123

// Incorrect
123_foo_bar
```

## Keywords

Keywords are special identifiers reserved for use as part of the programming language itself. You cannot use them for any other purpose.

Here is a list of keywords recognized by ANSI C89:

    auto break case char const continue default do double else enum extern
    float for goto if int long register return short signed sizeof static
    struct switch typedef union unsigned void volatile while

ISO C99 adds the following keywords:

    inline _Bool _Complex _Imaginary

and GNU extensions add these keywords:

    __FUNCTION__ __PRETTY_FUNCTION__ __alignof __alignof__ __asm
    __asm__ __attribute __attribute__ __builtin_offsetof __builtin_va_arg
    __complex __complex__ __const __extension__ __func__ __imag __imag__ 
    __inline __inline__ __label__ __null __real __real__ 
    __restrict __restrict__ __signed __signed__ __thread __typeof
    __volatile __volatile__

In both ISO C99 and C89 with GNU extensions, the following is also recognized as a keyword:

    restrict

## Constants

A constant is a literal numeric or character value, such as `5` or `m`. All constants are of a particular data type; you can use type casting to explicitly specify the type of a constant, or let the compiler use the default type based on the value of the constant.

* [Integer Constants](#integer-constants)
* [Character Constants](#character-constants)
* [Real Number Constants](#real-number-constants)
* [String Constants](#string-constants)

### Integer Constants
### Character Constants
### Real Number Constants
### String Constants
## Operators
## Separators
## White Space
# Data Types
## Primitive Data Types
### Integer Types
### Real Number Types
### Complex Number Types
#### Standard Complex Number Types
#### GNU Extensions for Complex Number Types
## Enumerations
### Defining Enumerations
### Declaring Enumerations
## Unions
### Defining Unions
### Declaring Union Variables
#### Declaring Union Variables at Definition
#### Declaring Union Variables After Definition
#### Initializing Union Members
### Accessing Union Members
### Size of Unions
## Structures
### Defining Structures
### Declaring Structure Variables
#### Declaring Structure Variables at Definition
#### Declaring Structure Variables After Definition
#### Initializing Structure Members
### Accessing Structure Members
### Bit Fields
### Size of Structures
## Arrays
### Declaring Arrays
### Initializing Arrays
### Accessing Array Elements
### Multidimensional Arrays
### Arrays as Strings
### Arrays of Unions
### Arrays of Structures
## Pointers
### Declaring Pointers
### Initializing Pointers
### Pointers to Unions
### Pointers to Structures
## Incomplete Types
## Type Qualifiers
## Storage Class Specifiers
### Renaming Types
# Expressions and Operators
## Expressions
## Assignment Operators
## Incrementing and Decrementing
## Arithmetic Operators
## Complex Conjugation
## Comparison Operators
## Logical Operators
## Bit Shifting
## Bitwise Logical Operators
### Pointer Operators
### The sizeof Operator
### Type Casts
### Array Subscripts
### Function Calls as Expressions
### The Comma Operator
### Member Access Expressions
### Conditional Expressions
### Statements and Declarations in Expressions
### Operator Precedence
### Order of Evaluation
#### Side Effects
#### Sequence Points
#### Sequence Points Constrain Expressions
#### Sequence Points and Signal Delivery
# Statements
## Labels
## Expression Statements
## The if Statement
## The switch Statement
## The while Statement
## The do Statement
## The for Statement
## Blocks
## The Null Statement
### The goto Statement
### The break Statement
### The continue Statement
### The return Statement
### The typedef Statement
# Functions
## Function Declarations
## Function Definitions
## Calling Functions
## Function Parameters
## Variable Length Parameter Lists
## Calling Functions Through Function Pointers
## The main Function
## Recursive Functions
## Static Functions
### Nested Functions
# Program Structure and Scope
## Program Structure
## Scope
# A Sample Program
## hello.c
## system.h
# Appendix A Overflow
## Basics of Integer Overflow
## Examples of Code Assuming Wraparound Overflow
## Optimizations That Break Wraparound Arithmetic
## Practical Advice for Signed Overflow Issues
## Signed Integer Division and Integer Overflow
# GNU Free Documentation License
# Index