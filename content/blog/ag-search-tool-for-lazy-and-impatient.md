+++
author = "Ramz"
categories = ["DevOps"]
date = "2016-08-28T19:05:07+10:00"
draft = false
title = "Ag: A search tool for the Lazy and the Impatient"
description = "Learn about Ag, the silver searcher"
type = "post"
+++

---

In software jargon, grep is a word for search. Most folks in software world grep for text all the time. If you are like me, lazy and impatient, you need a search tool which makes you

1. To do less work. (Less Typing)
2. To Wait less for output


[Ag](https://github.com/ggreer/the_silver_searcher) is the right tool for you.

---

### [Ag](https://github.com/ggreer/the_silver_searcher) help you to do less work
Typing ag is just 2 letters grep is 4 letters. Hurray, That is 50% less typing.
Not just that, how many times if you are searching a large repository you have to type something like this to avoid

``` shell
grep -r --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn} text_to_search
```


With ag it is just

``` shell
ag text_to_search
```


If you want to search just specific file type in grep

``` shell
find . -name "*.html" --exec grep "text_to_search" {} \;
```


In Ag, it is just

``` shell
ag --html text_to_search
```

Ag has about 80 odd file types where you can filter

### Ag makes you to wait less
Below is the performance measure between grep and ag on my laptop searching for the word “libhttp-parser”
To be fair i have aliased grep to be

``` shell
alias grep='grep -r --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn}'
```


Ag Performance

``` text
$ time ag libhttp-parser
3.96s user
11.61s system
97% cpu
15.958 total

```

Grep Performance

``` text
$ time grep -r "libhttp-parser" .
135.29s user
29.10s system
54% cpu
5:03.01 total
```

**Result:** *Ag is 20 times faster than grep.*

Yes, you can optimize grep with options but thats more work and more keystrokes to do that and not so simple.
For someone who is lazy, impatient, ag is the right tool for you. Be a silver searcher.
