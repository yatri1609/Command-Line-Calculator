# Command Line Calculator

## What

This is a command-line calculator, written in C, supporting the standard mathematical operations and a set of functions. Commands can be entered in standard infix syntax, with parentheses denoting nonstandard order of operations. You know, like you were taught in elementary and middle school.

### Operators
*	`+` Addition
*	`-` Subtraction
*	`*` Multiplication
*	`/` Division
*	`^` Exponent
*	`%` Modulus

### Functions
*	`abs(...)` Absolute value
*	`floor(...)` Floor
*	`ceil(...)` Ceiling
*	`sin(...)` Sine
*	`cos(...)` Cosine
*	`tan(...)` Tangent
*	`arcsin(...)` Arcsine
*	`arccos(...)` Arccosine
*	`arctan(...)` Arctangent
*	`sqrt(...)` Square root
*	`cbrt(...)` Cube root
*	`log(...)` Logarithm
*	`exp(...)` Exponentiation (e^x)
*	`min(...)` Minimum
*	`max(...)` Maximum
*	`sum(...)` Summation
*	`mean(...)` Mean
*	`avg(...)` Mean
*	`median(...)` Median
*	`var(...)` Variance

## How

Computation begins with the tokenization of the input string, maintaining original infix order. They are then converted to postfix notation (Reverse Polish Notation) for evaluation using the [shunting-yard algorithm][sy]. As operators are pushed onto the postfix stack, terms are evaluated.

[sy]: http://en.wikipedia.org/wiki/Shunting_yard_algorithm "Wikipedia article on the shunting-yard algorithm"

## Building and Running

Build with `make`. Clean with `make clean`. Run with `./calc`. Type any mathematical expression, for example, `3*(2^4) - 3*floor(2 * sin(3.14 / 2))` and press the Enter key. Type `quit` to close. Type `up` to see the previous expression and `down` to see the next expression after the expression seen on the terminal.

There is a `-r` command line option which removes the `=` from the output, outputting only the result value. This is designed for use in situations such as shell scripting, where only the raw, unprocessed value is desired.

There is a `-m` command line option which sets the maximal length of a token. Default is 512 characters.
