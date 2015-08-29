Using nbstripout

Add the following in the file `.git/config`:

    [filter "stripoutput"]
           clean = "scripts/nbstripout"
           smudge = cat
           required

