# Compiler Construction Project

## Overview

This project, part of the Compiler Construction unit, focuses on implementing a compiler that includes a lexer and parser. The compiler's primary goal is to process input strings, break them down into tokens using the lexer, and then determine if the resulting tokens, when parsed, form a palindrome.

## Components

### Lexer

The lexer, implemented in Python, serves as the initial phase of the compiler. It takes source code or input strings and tokenizes them into individual units, such as identifiers, numbers, and operators. The lexer uses regular expressions to define patterns for different token types and efficiently extracts them from the input.

The `lexer` function, defined in the code, uses a predefined set of token patterns to categorize elements in the input string. Each token is represented as a tuple containing its type and the actual value.

### Parser

The parser, implemented as the `parse` function, generates an Abstract Syntax Tree (AST) from the tokens produced by the lexer. In this project, the parser is specifically designed to handle palindrome checking. It defines functions to parse expressions and palindromes, and it raises a `SyntaxError` for invalid input.

### Palindrome Checker

The `is_palindrome` function uses a Recursive Descent Parser to check whether a given string or number is a palindrome. It leverages the parser's capabilities to determine if the input, when treated as a palindrome, satisfies the defined grammar rules.

## Example Usage

To demonstrate the functionality of the compiler, a simple example is provided in the code. The user is prompted to enter a string or number, which is then passed through the lexer to tokenize the input. The resulting tokens are parsed to generate an AST, and the palindrome checker evaluates whether the input is a palindrome or not.

```python
# Example Usage:
input_text = input("Enter a string or number: ")
tokens = lexer(input_text)
parsed_ast = parse(tokens)
is_input_palindrome = is_palindrome(parsed_ast[1])

if is_input_palindrome:
    print(f"The input '{parsed_ast[1]}' is a palindrome.")
else:
    print(f"The input '{parsed_ast[1]}' is not a palindrome.")
