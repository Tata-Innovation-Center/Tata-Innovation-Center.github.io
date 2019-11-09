---
layout: default
title: Python List
parent: Python
nav_order: 2
mathjax: true
date: 2019-11-09 12:00:00
---

## Python List

1. list.index(elt) search the elt and return the index with Time Complexity O(n).
2. list[:] returns a shallow copy of list, equivalent to "list.copy()", "list(list)", "copy.copy(list)"; If the list contain objects, you can use deep copy "copy.deepcopy(list)".
3. list[:] and list[i,j] return an new list for sure.
4. list.pop() remove and return the last element in the list，Time Complexity O(1)；list.pop(0) remove and return the first element in the list，BUT then move the following element 1 position up, Time Complexity O(n).
