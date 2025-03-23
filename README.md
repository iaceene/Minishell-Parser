Here's a more readable and well-structured `README.md`:  

---

# 🐚 Minishell Parser  

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
git clone https://github.com/yaajagro/minishell-parser.git
cd minishell-parser
make
./minishell
```

## Example Commands & Parsing Output
```
yaajagro@e1r7p7 $ ls -la
CMD [ls]
ARG [-la]

yaajagro@e1r7p7 $ ls -la | < file1 < file2 cat -e
CMD [ls]
ARG [-la]
infile [file1]
infile [file2]
CMD [cat]
ARG [-e]

yaajagro@e1r7p7 $ cat <<eof
> this is herdoc
> eof
CMD [cat]
herdoc fd [4] content [this is herdoc]

yaajagro@e1r7p7 $ echo $PATH
CMD [echo]
ARG [/home/yaajagro/bin:/usr/local/sbin:/usr/bin:/sbin:/bin]
```

## 👤 Author  
Developed by **[Yassine Ajagrou](https://github.com/iaceene)** as part of the **1337**. 
