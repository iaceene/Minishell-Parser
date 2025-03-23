# 🐚 Minishell Parser

![Alt Text](/img/perv.png)

```diff
+ yaajagro@elr7p7 $ ls -la
- COMMAND --> [ls] ARG [-la]

+ yaajagro@elr7p7 $ ls | ls -la | cat -e | grep $USER
- COMMAND --> [ls]
- PIPED TO
- COMMAND --> [ls] ARG [-la]
- PIPED TO
- COMMAND --> [cat] ARG [-e]
- PIPED TO
- COMMAND --> [grep] ARG [yaajagro]

+ yaajagro@elr7p7 $ ls > file1 < file2 >> appFile
- COMMAND --> [ls]
- OUTFILE [file1]
- INFILE [file2]
- APPEND [appFile]

+ yaajagro@elr7p7 $ << eof cat -e | ls -la
+ > this heredoc
+ > eof
- COMMAND --> [cat] ARG [-e]
- HERDOC fd [4] content [this heredoc]
- COMMAND --> [ls] ARG [-la]n style="color: blue;">COMMAND --> [ls] ARG [-la]</span><br>
```
## 📌 Overview  
This repository contains the **parsing module** for a custom **Minishell** implementation in C. The parser is responsible for:  
🔹 **Lexical analysis** – Tokenizing user input into meaningful components.  
🔹 **Syntax validation** – Ensuring correct command structure and detecting errors.  
🔹 **Expansion handling** – Processing environment variables and special characters.  
🔹 **Command structuring** – Organizing parsed data for execution.  

## Project Structure
```
components/parser/
├── expander/
│   ├── expander.c
│   ├── expander_utiles.c
│   ├── expander_utiles_tree.c
│   ├── expander_utiles_two.c
│   ├── handlers.c
├── herdoc/
│   ├── herdoc.c
│   ├── herdoc_utile_one.c
├── init/
│   ├── parser.c
│   ├── parser_utiles.c
├── lexer/
│   ├── final_step.c
│   ├── lexer.c
│   ├── lexer_utiles.c
│   ├── syntax_checker.c
│   ├── syntax_utiles.c
│   ├── syntax_utiles_two.c
├── prompt/
│   ├── get_cli.c
│   ├── prompt.c
│   ├── prompt_utiles.c
└── parser.h
```

## ✨ Features  
✅ Tokenizes shell commands into structured data.  
✅ Supports pipes (`|`), redirections (`>`, `<`), and heredocs (`<<`).  
✅ Handles **single** (`'`) and **double** (`"`) quotes correctly.  
✅ Expands **environment variables** (`$VAR`).  
✅ Validates syntax before execution.  

# Minishell Parser


## Features
- **Lexical Analysis**: Tokenizes input commands.
- **Syntax Checking**: Validates command structures.
- **Expansion**: Handles variables, wildcards, and heredoc.
- **Command Parsing**: Builds AST-like structures for execution.
- **Redirections & Pipes**: Parses input/output redirections and command pipelines.

## Installation & Usage
```sh
git clone https://github.com/iaceene/Minishell-Parser.git
cd Minishell-Parser
# if you are using Mac
./Parser_Mac
# if you are using Linux
./Parser_Linux
```

## Example Commands & Parsing Output
```
yaajagro@e1r7p7 $ ls -la
COMMAND --> [ls] ARG [-la]

yaajagro@e1r7p7 $ ls | ls -la | cat -e | grep $USER
COMMAND --> [ls] 
PIPED TO
COMMAND --> [ls] ARG [-la]
PIPED TO
COMMAND --> [cat] ARG [-e]
PIPED TO
COMMAND --> [grep] ARG [yaajagro]

yaajagro@e1r7p7 $ ls > file1 < file2 >> appFile
COMMAND --> [ls] 
OUTFILE [file1]
INFILE [file2]
APPEND [appFile]

yaajagro@e1r7p7 $ << eof cat -e | ls -la
> this heredoc
> eof
COMMAND --> [cat] ARG [-e]
HERDOC fd [4] content [this heredoc]
COMMAND --> [ls] ARG [-la]
```

## 👤 Author  
Developed by **[Yassine Ajagrou](https://github.com/iaceene)** as part of the **1337**. 
