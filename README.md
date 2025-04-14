# Matrix Language Interpreter
Project for AGH course Theory of Compiling. This project is an interpreter for a simple programming language designed to perform operations on matrices. It was developed through a series of structured steps, including lexical analysis, parsing, AST construction, semantic analysis, and interpretation.

## Features

### 🔍 Lexical Analyzer (Scanner)

Detects a wide range of tokens, including:

- Arithmetic and matrix operators: `+`, `-`, `*`, `/`, `.+`, `.-`, `.*`, `./`
- Assignment operators: `=`, `+=`, `-=`, `*=`, `/=`
- Relational operators: `<`, `>`, `<=`, `>=`, `!=`, `==`
- Parentheses and brackets: `()`, `[]`, `{}`
- Range operator: `:`
- Matrix transposition: `'`
- Comma and semicolon: `,`, `;`
- Keywords: `if`, `else`, `for`, `while`, `break`, `continue`, `return`, `eye`, `zeros`, `ones`, `print`
- Identifiers, integers, floats, and strings

Whitespace and comments (starting with `#`) are ignored.

### 🧩 Parser

Recognizes full language constructs such as:

- Binary and relational expressions
- Unary negation and transposition
- Matrix initialization and slicing
- Special matrix functions
- Assignments with all supported operators
- `if-else` statements
- `while` and `for` loops
- `break`, `continue`, and `return` statements
- `print` statements
- Compound instructions (blocks)

### 🌲 Abstract Syntax Tree (AST)

Constructs a structured AST that includes:

- Expressions and assignments
- Control flow structures
- Matrix and array operations

### ✅ Semantic Analyzer

Performs semantic validation, detecting issues like:

- Inconsistent matrix dimensions in initialization
- Out-of-bound indexing (for constant indices)
- Incompatible types in binary operations
- Invalid parameters in matrix functions (`eye`, `zeros`, `ones`)
- Misuse of control statements (`break`/`continue` outside loops)

### 🧠 Interpreter

Evaluates AST nodes using the Visitor pattern with decorators. Execution only proceeds if both syntactic and semantic analysis succeed.

- Uses a stack-based memory model to manage scopes and variable lifetimes
- Implements `break` and `continue` using exceptions for proper control flow handling
