## Introduction to Compilers

There are two major approaches for implementing programming languages:
1. Compilers
	Compilers takes a __Program__ and process it and produce an __Executable__ or __Byte Code__. Then this run separately on __Data__ and produce the __Output__.


2. Interpreters
	Interpreters takes the __Program__ and __Data__ and produce the __Output__.
	It doesn't do any processing before actually running the program. 

FORTRAN 1 (1957) is the first successful compiler design and still modern compilers preserve the outline of FORTRAN 1. 

FORTRAN 1 consists of 5 phases:
	1. Lexical Analysis
	2. Parsing
		- Lexical Analysis & Parsing takes care of the __Syntactic__ aspect of the language. 
	3. Semantic Analysis
		- Takes care of more semantic aspects, things like __types__ and __scope__.
	4. Optimization
		- Collection of transformations on the program to either make it __run faster__ or __use less memory__.
	5. Code Generation
		- Translation of code to some other language (It can be machine code, Byte code, or even another high level programming language)

## Structure of a Compiler

The first step of understanding a program is to __recognize the words__.

- Therefore, the goal of __Lexical Analysis__ is to divide the program text into "words" or "token". 

- Once words are understood, the next step is to understand sentence structure, which is called __Parsing__.
	__Parsing__ means diagramming sentences. (The diagram is usually a tree)

Example:
	if x == y then z=1; else z=2;

![[Pasted image 20240208221436.png]]

- Once sentence structure is understood, we can try to understand the __meaning__, which is a very difficult task.
	Compilers perform limited __semantic analysis__ to catch inconsistencies.
	If the program is self-inconsistent, compiler catch this and report errors but they don't know what the program is supposed to do.

	There are a lot of ambiguities in semantic analysis, therefore Programming languages define strict rules to avoid such ambiguities.

	Compilers perform many semantic checks besides variable bindings.

- Optimization Automatically modify programs so that they __Run faster__ and/or __Use less memory__ and many more.

- __Code Generation__ (Code Gen) produces a translation into another language, usually assembly code.

## The Economy of Programming Language


