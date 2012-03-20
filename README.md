re-env
======

This is a simple bash function that solves the problem of activating a Python
virtualenv that is in the current directory or a parent directory. It
recursively searches for a directory named venv and activates the bin/activate
script inside that directory.

Rather than storing all virtualenvs in a single directory, as required by the
workon script included with virtualenv-wrappers, this script assumes that the
virtualenv for a given codebase is in the same directory as the code it is
being maintained for. For example, my code looks something like this:

/home/dusty/code/
+ project1
| + src
| | + pkg1
| | + pkg2
| + doc
| + venv
+ project2
| + src
| + venv27
| + venvpypy
+ project3
| + venv

If I am in the `code/project1/src/pkg1` directory, I can run the `v` function and it will
find and activate the virtualenv script in `code/project1/venv/bin/activate`. If I am in
the `project2/src` directory and I run the `v venvpypy` command, it will find and activate
the virtualenv in `code/project2/venvpypy/bin/activate`.

The easiest way to install is to copy the function in your ~/.bashrc.

Note that I am a Python programmer, this may not be the prettiest bash you've seen.
