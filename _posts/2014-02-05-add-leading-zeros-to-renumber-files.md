---
kind: article
title: "Add leading zeros to renumber files"

created_at: 2014-02-05 10:48

---

A quick one... pretty simple but I wanted to make note of it.

I unwisely numbered the files in a folder like so:

```
1.txt
2.txt
...
9.txt
10.txt
11.txt
12.txt
```

So their alphanumeric order is not the same as the numeric order. Is there 
a quick way in the shell to renumber these with leading zeros? 
[Of course.](http://stackoverflow.com/questions/3672301/linux-shell-script-to-add-leading-zeros-to-file-names)

    for a in [0-9]*.txt; do                     # match numbered files
        mv $a `printf %02d.%s ${a%.*} ${a##*.}` # replace number with 2-digit ver.
    done