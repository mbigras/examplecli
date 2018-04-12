# Somecli

> A command line tool written in Ruby, designed to provide a starting place for thinking about command line tools.

## Installation

```
git clone https://github.gapinc.com/mbigras/somecli
cd somecli
```

## Sample reading

* https://unix.stackexchange.com/questions/430542/are-there-accepted-conventions-for-argv-options-environment-variables-stdin

## Usage examples

Running the tool with no arguments.

```
./somecli
hello world!
"hello world!"
[]
hello world
hello world
ls: idontexist: No such file or directory
```

Running the tool with 3 arguments

```
./somecli foo bar fail
hello world!
"hello world!"
["foo", "bar", "fail"]
Doing something with foo...
Doing something with bar...
Doing something with fail...
hello world
hello world
ls: idontexist: No such file or directory
```

Running the tool with 3 arguments, but redirecting standard error.

```
./somecli foo bar fail 2>/dev/null
hello world!
"hello world!"
["foo", "bar", "fail"]
Doing something with foo...
Doing something with bar...
hello world
hello world
```

Running the tool with 3 arguments, but redirecting both standard out and standard error.

```
./somecli foo bar fail &>/dev/null
```

Checking exit status on success

```
./somecli foo bar baz &> /dev/null
echo $?
0
```

Checking exit status on failure

```
./somecli foo bar fail &> /dev/null
echo $?
1
```