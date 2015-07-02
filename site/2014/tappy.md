%YAML 1.1
---
blog: True
title: tappity tap TAP tappy
date: 2014-03-17T12:00:00Z
summary: Introduction of TAP tools for Python
template: writing.j2

---
<img class='book' src='tap.jpg'>

I am pleased to announce a new Python project aimed to bridge Python to
broader testing areas. The new project is called **tappy** and its goal is to
generate test information in the [Test Anything
Protocol](http://testanything.org/) (TAP).

[tappy](http://tappy.readthedocs.org/en/latest/) converts Python
`unitest.TestCase` based results into TAP results with either a
`TAPTestRunner` that behaves just like the standard library `TextTestRunner`
or with a [nose](https://nose.readthedocs.org/en/latest/) plugin.

tappy popped into existence because I work in a very heterogeneous programming
environment at work. The details of that work won't excite the average reader,
but the job consists of C++, Python, Perl, and plenty of shell scripts. All
of these languages have various tests to report status and each testing
environment is different. Unfortunately, the data from multiple languages
cannot be entirely aggregated into one view.

The Test Anything Protocol can solve the problem of test aggregation by
providing a *lingua franca* for tests. If each language generates results in
the TAP format, the data can be normalized into that common view. The common
view can give a sense of the health of the whole system. In such an
environment, tappy acts as the TAP source for Python based test suites.

My long term goal for tappy is to make it available to as many versions of
Python as possible and as many different Python test tools as possible (e.g.,
nose and trial).

You can follow tappy development on [GitHub](https://github.com/mblayman/tappy)
or get tappy from [PyPI](https://pypi.python.org/pypi/tap.py). The `tappy` name
was taken on PyPI by the "Tidal Analysis Program" so I had to use `tap.py`
instead.

```bash
$ pip install tap.py
```