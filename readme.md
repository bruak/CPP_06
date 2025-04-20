# CPP Module 06

This repository contains the exercises for CPP Module 06, focusing on C++ type casting.

## Overview

This module explores the various type casting operators available in C++, including static_cast, dynamic_cast, reinterpret_cast, and const_cast. The exercises demonstrate practical applications of these casting operators and their use cases, highlighting the differences between them and when to use each one appropriately.

## Exercises

### Exercise 00: Scalar Conversion

An implementation of a `ScalarConverter` class that converts scalar types between different C++ primitive data types.

#### Features:
- Conversion between char, int, float, and double types
- Handling of special cases like NaN, infinity, and non-displayable characters
- Detection and conversion of different numeric formats
- Proper exception handling for impossible conversions

#### Implementation Details:
- String parsing to identify type of input
- Use of static_cast to perform conversions between different scalar types
- Precise output formatting with appropriate precision
- Detection of overflow and other conversion edge cases

### Exercise 01: Serialization

A demonstration of `reinterpret_cast` through the implementation of a `Serializer` class that converts objects to raw memory representations and back.

#### Features:
- Serialization of pointer to uintptr_t (an integer type capable of holding a pointer)
- Deserialization of uintptr_t back to original pointer type
- Memory address preservation throughout the conversion process

#### Implementation Details:
- Use of reinterpret_cast to convert between pointer types and integer representations
- Data integrity preservation during conversion
- Safe handling of memory address conversions
- Understanding of memory representation at a low level

### Exercise 02: Identify Real Type

An exploration of `dynamic_cast` and runtime type information (RTTI) through a base class hierarchy and type identification functions.

#### Features:
- Base class with derived classes (A, B, C)
- Random instantiation of derived classes
- Identification of actual object type at runtime using pointers
- Identification of actual object type at runtime using references

#### Implementation Details:
- Base class with virtual destructor to enable proper polymorphism
- Using dynamic_cast to check object types at runtime
- Handling of failed casts with both pointer and reference approaches
- Implementation of different strategies for type identification

## Casting Operators in C++

### static_cast

- Used for conversions between related types (like int to float)
- Provides compile-time type checking
- Cannot remove const or volatile qualifiers
- Safer than C-style casts but cannot perform all types of conversions
- Used in exercise 00 for converting between scalar types

### dynamic_cast

- Used primarily for downcasting (base class pointer to derived class pointer)
- Relies on Run-Time Type Information (RTTI)
- Returns nullptr (for pointers) or throws std::bad_cast (for references) if casting fails
- Only works on polymorphic types (classes with at least one virtual function)
- Used in exercise 02 for identifying derived types from a base pointer

### reinterpret_cast

- Performs low-level reinterpretation of bit patterns
- Extremely powerful but potentially dangerous
- No checks performed, simply reinterprets memory representation
- Typically used for system-level programming or interfacing with non-C++ code
- Used in exercise 01 for converting between pointers and integer types

### const_cast

- Used to add or remove const/volatile qualifiers
- Only changes the constness of an expression, not its value
- Should be used cautiously as modifying a previously const value leads to undefined behavior
- Useful when interfacing with APIs that don't properly use const

## Compilation

Each exercise comes with a Makefile that supports the following commands:
- `make`: Compile the program
- `make clean`: Remove object files
- `make fclean`: Remove object files and executable
- `make re`: Recompile the entire program

## Requirements

- C++ compiler with C++98 standard support
- Linux/macOS environment
- All code must compile with the following flags:
```
c++ -Wall -Wextra -Werror -std=c++98
```

## Notes

These exercises demonstrate important C++ concepts such as:
- Type safety and how casting can circumvent it when necessary
- The importance of choosing the right cast for each situation
- How RTTI works in C++ and when to use it
- Memory representation of different data types
- Proper error handling during type conversions
- The limits of each casting operator and their appropriate use cases