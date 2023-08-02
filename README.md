# vim-env-syntax

This plugin provides Vim syntax highlighting for `.env` files.

Usually, `.env` files are detected as filetype `sh`, because they look like
– and often are – valid shell code.  However, there is a file type definition
of `.env` files that is much simpler.  Tools following this definition, such as
`kubectl`, do not parse `.env` files like a shell would.  Instead, lines are
very simply split at the first equal sign to determine variable names and
values.  No parsing of the values is performed, leading to, e.g., quote
characters becoming part of the literal variable values.

The `env.vim` syntax definition only highlights relevant syntax for this
use-case.  Besides variable names and the first equal sign, it highlights
potential pitfalls (see the included `examples.env` file).  It does not
highlight any other syntax that would otherwise be significant to a shell.
