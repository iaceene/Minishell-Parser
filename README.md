Here's a more readable and well-structured `README.md`:  

---

# 🐚 Minishell Parser  

## 📌 Overview  
This repository contains the **parsing module** for a custom **Minishell** implementation in C. The parser is responsible for:  
🔹 **Lexical analysis** – Tokenizing user input into meaningful components.  
🔹 **Syntax validation** – Ensuring correct command structure and detecting errors.  
🔹 **Expansion handling** – Processing environment variables and special characters.  
🔹 **Command structuring** – Organizing parsed data for execution.  

## ✨ Features  
✅ Tokenizes shell commands into structured data.  
✅ Supports pipes (`|`), redirections (`>`, `<`), and heredocs (`<<`).  
✅ Handles **single** (`'`) and **double** (`"`) quotes correctly.  
✅ Expands **environment variables** (`$VAR`).  
✅ Validates syntax before execution.  

## 📂 Project Structure  
```
📁 minishell-parser/
 ├── parser.h         # Header file defining parser structures & functions
 ├── lexer.c          # Tokenization logic
 ├── syntax.c         # Syntax validation functions
 ├── expander.c       # Variable expansion & quote handling
 ├── utils.c          # Helper functions
 ├── README.md        # Project documentation
```

## 🚀 Installation  
Clone the repository:  
```sh
git clone https://github.com/iaceene/minishell-parser.git
cd minishell-parser
```
Compile it as part of your **Minishell** project.

## 🛠 Usage  
Include `parser.h` in your project and use `lexer_init()` to tokenize shell input. Example:  
```c
t_node *tokens = lexer_init("echo $HOME | grep user");
```

## 👤 Author  
Developed by **[Yassine Ajagrou](https://github.com/iaceene)** as part of the **42** curriculum.  

---

This version improves readability with spacing, emojis, and a clearer structure. Let me know if you need further tweaks! 🚀