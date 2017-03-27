# lit 🔥

`lit` is a general implementation of "literate programming", supporting all languages.

## Literate Programming

Literate programming is a way to write more readable programs with a documentation-first approach. It's great for writing tutorials, blog posts, or any kind of code that is meant to be shared.

There are a few specific implementations of this concept:

* [Literate Python](https://github.com/bslatkin/pyliterate)
* [Literate CoffeeScript](http://coffeescript.org/#literate)

`lit` generalizes that concept, allowing you to run any Markdown file with indented code blocks.

Here's an example in Python:

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
> lit python test.lit.python
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
lit coffee test.lit.coffee
lit python test.lit.python
```
