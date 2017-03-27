# lit 🔥

`lit` lets you use Markdown for literate programming in any language.

For Vim syntax highlighting support see [vim-lit](https://github.com/spro/vim-lit).

## What is Literate Programming?

[Literate programming](https://en.wikipedia.org/wiki/Literate_programming) is a way to write more readable programs by combining documentation with code. It's great for writing tutorials, blog posts, or any kind of code that is meant to be shared.

> The main idea is to treat a program as a piece of literature, addressed to human beings rather than to a computer.
> &mdash; Donald Knuth (inventor)

There are a few specific implementations of this concept:

* [Literate Python](https://github.com/bslatkin/pyliterate)
* [Literate CoffeeScript](http://coffeescript.org/#literate)

## What is lit?

`lit` allows you to execute a literate version of any program written as indented Markdown code blocks.

Here's an example of a literate Python script `test.py.lit`:

```
# My Python Script

This program prints a few numbers. Specifically `n` numbers.

    n = 5

    for i in range(n):
        print(i)
```

This program can be run as a regular Python script through `lit`:

```
> lit python test.py.lit
0
1
2
3
4
```

While opened in a Markdown viewer it looks like:

![](https://i.imgur.com/QnR52CC.png)

## Installation

Copy `lit` to your path.

## Usage

**`lit [program] [filename] [args...]`**

`lit` will first turn your .lit file into an .unlit file by removing everything except the indented blocks. It then runs that .unlit file via `[program]`, passing on extra arguments:

```
lit python test.py.lit -n 500
=> python test.py.lit.unlit -n 500
```

Certain programs require command line options to be passed before the program name, in which case the `-b` (for before) option should be used:

```
lit -b gcc test.cpp.lit -x c++ -o test
=> gcc -x c++ -o test test.cpp.lit.unlit
```
