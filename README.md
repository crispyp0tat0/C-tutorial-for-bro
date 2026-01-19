# C-tutorial-for-bro
This repo is not for you... this is for bro. If you're not bro, don't open this repo

Based off of The GNU C Reference Manual

## The main function

This function is needed for ever C program... without it, the program won't compile

You can do it in on of 2 ways:

```C
int main(void) {...}
```

if you're not using the Command-line interface (CLI)

or

```C
int main(int argc, char *argv[]) {...}
```

if you need the CLI

e.g.:

```C
#include <stdio.h> // You must include this to use printf

int main(void)
{
    printf("hello, world\n");
    return 0; // You can omit this... but returning in main makes me happy
}
```

The return type is what goes before the function name... in main's case, it's int... and it can only be int for main tbh.

## Lexical Elements

### Identifiers (e.g., variable names, function names, etc.)

Identifiers are sequences of characters used for naming variables, functions, new data types, and preprocessor macros. You can include letters, decimal digits, and the underscore character ‘_’ in identifiers.

The first character of an identifier cannot be a digit.

Lowercase letters and uppercase letters are distinct, such that foo and FOO are two different identifiers.

e.g.:

```C
// Correct
int foo;
int FOO;
int foo_;
int _foo;
int foo_bar;
int foo123;

// Incorrect
int 1_foo;
int 1foo_;
```

### Keywords

Keywords are special identifiers reserved for use as part of the programming language itself. You cannot use them for any other purpose.

Here is a list of keywords recognized by ANSI C89:

```C
auto break case char const continue default do double else enum extern
float for goto if int long register return short signed sizeof static
struct switch typedef union unsigned void volatile while
```

ISO C99 adds the following keywords:

```C
inline _Bool _Complex _Imaginary
```

and GNU extensions add these keywords:

```C
__FUNCTION__ __PRETTY_FUNCTION__ __alignof __alignof__ __asm
__asm__ __attribute __attribute__ __builtin_offsetof __builtin_va_arg
__complex __complex__ __const __extension__ __func__ __imag __imag__ 
__inline __inline__ __label__ __null __real __real__ 
__restrict __restrict__ __signed __signed__ __thread __typeof
__volatile __volatile__ 
```

Yes bro... you can't use these as variable, function, data type, or macro names.

### Constants

A constant is a literal numeric or character value, such as 5 or 'm'. All constants are of a particular data type; you can use type casting to explicitly specify the type of a constant, or let the compiler use the default type based on the value of the constant.

#### Integer Constants

An integer constant is a sequence of digits, with an optional prefix to denote a number base.

If the sequence of digits is preceded by 0x or 0X (zero x or zero X), then the constant is considered to be hexadecimal (base 16). Hexadecimal values may use the digits from 0 to 9, as well as the letters a to f and A to F. Here are some examples:

```C
0x2f
0x88
0xAB43
0xAbCd
0x1
```

If the first digit is 0 (zero), and the next character is not ‘x’ or ‘X’, then the constant is considered to be octal (base 8). Octal values may only use the digits from 0 to 7; 8 and 9 are not allowed. Here are some examples:

```C
057
012
03
0241
```

In all other cases, the sequence of digits is assumed to be decimal (base 10). Decimal values may use the digits from 0 to 9. Here are some examples:

```
459
23901
8
12
```

There are various integer data types, for short integers, long integers, signed integers, and unsigned integers. You can force an integer constant to be of a long and/or unsigned integer type by appending a sequence of one or more letters to the end of the constant:

```
u
U
Unsigned integer type.

l
L
Long integer type.
```

For example, 45U is an unsigned int constant. You can also combine letters: 45UL is an unsigned long int constant. (The letters may be used in any order.)

Both ISO C99 and GNU C extensions add the integer types long long int and unsigned long long int. You can use two ‘L’s to get a long long int constant; add a ‘U’ to that and you have an unsigned long long int constant. For example: 45ULL.

Bro... 0x00000000u is unsigned 0
though this doesn't make sense... coz you can't represent negative values in HEXADECIMAL, as 0xFF is either the largest value in one byte, or -1.