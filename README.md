# lit 🔥

`lit` is a general implementation of "literate programming", supporting any language.

For Vim syntax highlighting, see [vim-lit](https://github.com/spro/vim-lit).

## What is Literate Programming?

[Literate programming](https://en.wikipedia.org/wiki/Literate_programming) is a way to write more readable programs, by combining documentation with code. It's great for writing tutorials, blog posts, or any kind of code that is meant to be shared.

> The main idea is to treat a program as a piece of literature, addressed to human beings rather than to a computer.
> &mdash; Donald Knuth (inventor)

There are a few specific implementations of this concept:

* [Literate Python](https://github.com/bslatkin/pyliterate)
* [Literate CoffeeScript](http://coffeescript.org/#literate)

## What is lit?

`lit` generalizes the idea of literate programming to allow you to write a literate version of any program in indented Markdown code blocks.

Here's an example of a literate Python script, `test.py.lit`:

```
# My Python Script

This program prints a few numbers. Specifically `n` numbers.

    n = 5

    for i in range(n):
        print(i)
```

Rendered in a Markdown viewer, this looks like:

![](https://i.imgur.com/QnR52CC.png)

And run with `lit`:

```
> lit python test.py.lit
0
1
2
3
4
```

## Installation

Copy `lit` to your path.

## Usage

`lit` operates by first transforming your markdown file into an ".unlit" file by stripping out everything except the indented blocks. It then runs your specified file with the arguments. After executing it will delete the ".unlit" file.

**`lit [program] [filename] [args...]`**

For example:

```bash
lit coffee test.coffee.lit
lit python test.python.lit
```
