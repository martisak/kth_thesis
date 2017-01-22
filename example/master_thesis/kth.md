---
title: Titel på avhandling på en eller två rader
subtitle: By me!
author: Martin Isaksson
date:  December 2016
---

# Section

Here is some \index{general} text with a reference @Plain21:online, and here is a reference to a picture Figure \ref{fig:cc}. See also [@tom_pollard_2016_58490] for more tricks^[this is a footnote.].

## Subsection

![Creative Commons](images/cc.logo.large.png "Short caption"){ #fig:cc width=60% }

\lipsum[1]

| Column 1 | Column 2 |
| ------------- | ------------- |
| Cell 1-1 | Cell 1-2 |
| Cell 2-1 | Cell 2-2 |

Table: This is a table caption.

## Code samples

This is an example of inline code.

~~~ {caption="Hello World in Python" label=helloworld .python .numberLines}
def helloworld():
    return "Hello world!"
~~~

\cleardoublepage

# References

---
nocite: |
    @markdowncheatsheet, @martin_isaksson_2017_256752
---
