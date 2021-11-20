# test_docstring_and_sphinx

This is a template file to manage your research environment with doctest and document using sphinx.

## Flow

1. ```pip install sphinx```
2. create py file under src dir. (depends on your dir structure.)
3. write this kind of code with comments. 
```python
def print_sum(x, y):
    """print the sum of two numbers
    This function takes two numbers and prints the sum of them.
    The addition is done using the built-in function '+'.

    Parameters:
    -----------
    x: the first number
    y: the second number

    Examples:
    ---------
    >>> print_sum(1, 2)
    3
    >>> print_sum(-1, 2)
    1
    """
    print(x + y)
```
4. Pass the doctest using ```python -m doctest test.py```
4. create reST file ```sphinx-apidoc [OPTIONS] -o <OUTPUT_PATH> <MODULE_PATH>```
5. modify conf.py 
```python
<!-- Just comments out -->
import os
import sys
sys.path.insert(0, '（略）\\project\\src')

~~~~~

extensions = [
    'sphinx.ext.autodoc',
    'sphinx.ext.viewcode',
    'sphinx.ext.todo',
    'sphinx.ext.napoleon'
]
```
6. make html file. ```sphinx-build [options] <sourcedir> <outputdir> [filenames ...]```

## References
 - https://qiita.com/hmkz/items/0689cd85fb3e1adcda1a
 - https://helve-blog.com/posts/python/sphinx-documentation/
