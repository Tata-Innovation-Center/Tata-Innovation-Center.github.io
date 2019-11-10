---
layout: default
title: Python List
parent: Programming Language
nav_order: 2
mathjax: true
date: 2019-11-09 12:00:00
---
# Programming Language
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
## Time complexity of some basic Python List operations

1. list.index(elt) search the elt in the list and return the index with Time Complexity O(n).
2. list[:] returns a shallow copy of list, equivalents to "list.copy()", "list(list)", and "copy.copy(list)"; If the list contain objects, you can use deep copy "copy.deepcopy(list)".
3. list[:] and list[i:j] both return a new list.
4. list.pop() remove and return the last element in the list，Time Complexity O(1)；list.pop(0) remove and return the first element in the list，BUT then move all the following elements 1 position up, Time Complexity O(n).
