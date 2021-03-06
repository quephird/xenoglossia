# Xenoglossia

<blockquote class="twitter-tweet" lang="en"><p lang="en" dir="ltr">A programming language specifically designed such that ASTs generated by markov chain are likely to produce programs with meaningful effects</p>&mdash; mcc (@mcclure111) <a href="https://twitter.com/mcclure111/status/619713910552133632">July 11, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

Xenoglossia is a simple string manipulation language, akin to sed.
It was created with the goal of producing surprising, fun-to-read programs which can be generated in novel manners by a computer.

An introduction to the language and its syntax can be found in the [design document](doc/design.md), and the documentation of the builtin functions can currently be found in the docstrings of the [builtins module](xenoglossia/builtins.py).

# Installation

You can install this package using Python's `pip` package manager:

```
pip install xenoglossia
```

If you use Mac OS X, you can also install it using [Homebrew](http://brew.sh):

```
brew install mistydemeo/formulae/xenoglossia
```

Clone the repository, and then run:

```
python setup.py install
```

# Usage

Xenoglossia will install an executable named `xg`.
To run a program, call `xg --input STRING "xenoglossia program"`; for example:

```sh
xg --input "This is the input string" "sub 'input' 'output'"
```

You can also pipe input into stdin:

```sh
echo "This is the input string" | xg "sub 'input' 'output'"
```

# Sample programs

Replace two words in a sentence:

```
gsub "favorite" "favourite" gsub "color" "colour"
```

Rearrange the words in a sentence, then capitalize the new sentence:

```
burst " " shuffle capitalize
```

# TODO

* Add support for user-supplied modules of functions

# Known bugs

* Illegal function identifiers (for example, identifiers beginning with a number) are only flagged for the first function call in a series; otherwise the function call is simply skipped during parsing.
