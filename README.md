## Using nbstripout

nbstripout is a filter that removes numbering and output from jupyter notebooks.

The script `nbstripout` was found
[here](https://github.com/cfriedline/ipynb_template/blob/master/nbstripout) with inspiration
from [here](https://gist.github.com/minrk/6176788) (see the discussion there).

It is available on PyPI, so it is rather straightforward to use.

## Short

Install nbstripout:

    python3 -m pip install --user nbstripout

Add the following in the file `.git/config`:

    [filter "stripoutput"]
           clean = "nbstripout"
           smudge = cat
           required

and also write a `.gitattributes` file:

    *.ipynb filter=stripoutput

## Long

Whenever a [Jupyter](http://jupyter.org/) notebook (detected by the extension `.ipynb`) is
submitted to `git diff` or `git commit`, it is converted by the filter. The filter removes
all numbering (that might change upon execution) and the output (that might contain binary
data for figures, etc).
