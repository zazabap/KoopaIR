
# Structure of the compiler 


Usually the command line could accept the input command as follow 
```
    gcc hello.c -o hello
```

The compiler will convert the code into the executable. There are actually three steps from the code into the executable. 

1. Compile: convert the source code into the assembly 
2. Compilation? Convert the assembly into the object file. 
3. linkage : change the target file to the executable. 

The compiler designed just involve the first step we stated here.

## parser & lexer 

One example is from the 

```cpp
int main() {
  return 0;
}
```

```ebnf
CompUnit  ::= FuncDef;

FuncDef   ::= FuncType IDENT "(" ")" Block;
FuncType  ::= "int";

Block     ::= "{" Stmt "}";
Stmt      ::= "return" Number ";";
Number    ::= INT_CONST;
```

EBNF, Extended Backus-Naur Form, can be used to describe the programming language and its grammar. 

```
A ::=B
```
This represents we can replace A with B.

## 1.2 C/C++ analysis for parser and lexer

Here is the link for a complete C++ parser with a simple but complete example
[demo](https://www.gnu.org/software/bison/manual/html_node/A-Complete-C_002b_002b-Example.html).

* Flex: Ending symbol part, describe type of the token and class. 
* Bison: the EBNF itself, it will generate a LALR parser. 

The whole program structure will then be 
```txt 
src/main.cpp
src/sysy.l     # This is a lexer 
src/sysy.y     # This is a parser 
Makefile       # The makefile 
```

