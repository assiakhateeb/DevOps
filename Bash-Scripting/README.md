## Bash Scripting

### Resources

- [Chmod Calculator](https://chmodcommand.com/)

We start by creating a file with the `.sh` extension. For example `script.sh`. Then we write the script in it. For example:

Basic Script

```bash
#!/bin/bash

echo "Hello World"
```    

We can run this by `bash script.sh` or `./script.sh`. But the second will only work if the script is executable (permission to execute). We can make it executable by `chmod +x script.sh`. Now we can run it by `./script.sh`.

### Shebang

The first line of a bash script is called the shebang. It tells the system which interpreter to use to run the script. The shebang for bash is `#!/bin/bash`. The shebang for python is `#!/usr/bin/env python`. It vary from the langauge to language.

### Variables

It is placeholder for a value. Just like any other programming language. We use $ to access the variable. Eg: `$NAME`. We can also use `${NAME}`. The braces are used to make sure that the variable is not mistaken for a command.

```bash
#!/bin/bash

# Variable Declaration
NAME="John"

# Variable Usage

echo "My name is $NAME"
echo "My name is ${NAME}"
```

NOTE: We can create variables by `NAME="John"` through CLI, we can't use in the script beacuse it is not exported. We can export it by `export NAME="John"`. Now we can use it in the script.

But here is one more catch. If we exit the terminal and open a new one, the variable will be gone. To make it permanent, we can add it to the `.bashrc` file. It is a hidden file in the home directory. We can open it by `vi ~/.bashrc` or any other editor. We can add the variable to the file. Eg: `export NAME="John"`.

### User Input

We can take input from the user using the `read` command.

```bash
#!/bin/bash

echo "Enter your name: "
read NAME
echo "Hello $NAME, nice to meet you!"
```

### Arguments

We can pass arguments to the script. The arguments are stored in the `$1`, `$2`, `$3` and so on. `$0` is the name of the script.

Eg: `bash script.sh arg1 arg2`

```bash
#!/bin/bash

echo "First Argument: $1"
```

### Arthemetic Operations

We can do arthemetic operations in bash. We use the `(( ))` to do arthemetic operations.

```bash

```bash
#!/bin/bash

echo $(( 5 + 5 ))
```

#### Arthemetic Operators

- `+` - Addition
- `-` - Subtraction
- `*` - Multiplication
- `/` - Division
- `%` - Modulus

### Conditional Statements

We can use the `if` statement to check for a condition. The syntax is:

```bash
#!/bin/bash

if [ "$1" == "John" ]
then
    echo "Hello John"
    exit 1
elif [ "$1" == "Doe" ]
then
    echo "Hello Doe"
else
    echo "I don't know you"
fi
```

```bash
if [$1 == "hello"],then echo "Hello World", fi
```

#### Comparison Operators

- `==` - Equal to
- `>` - Greater than
- `<` - Less than
- `>=` - Greater than or equal to
- `<=` - Less than or equal to
- `!=` - Not equal to

#### Boolean Operators

- `-a` - And
- `-o` - Or
- `!` - Not

- `exit 1` - Exit the script with an error (non-zero exit code).

- $RANDOM gives a random number between 0 and 32767.
- $SHELL gives the path of the shell.
- $USER gives the username of the user.
- $HOSTNAME gives the hostname of the machine.

