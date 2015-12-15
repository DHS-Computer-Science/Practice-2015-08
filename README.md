# Practice 2015 - 08: Infiltrating the Enemy

## Background
S.H.I.E.L.D. is trying to learn more about HYDRA’s management structure so they
can figure out who is in charge at each level, and insert spies in the best
places. HYDRA’s management structure forms a tree-based hierarchy, and this is
stored as trees in infix and prefix form. Unfortunately, S.H.I.E.L.D. can only
understand trees in postfix form. We’ll discuss trees along with prefix, infix,
and postfix form below. Trees are some of the most important things in the
world. They convert the carbon dioxide you breath out into oxygen. They prevent
the erosion of coastlines, and provide a habitat for a variety of different
animals. Most importantly, trees allow us to represent a hierarchical structure.

Here is an example of a tree:
```
     1
   /   \
  2     3
 / \   / \
4   5 6   7
```
Here is another example of a tree:
```
   1
  / \
  2  3
  \   \
  5    6
 /  \
4    7
```
However, as computer scientists, it is hard for us to represent trees, since
keyboards are notoriously bad at free form drawing. There are three ways to
represent trees with text by printing out each of the individual values. But if
we are going to print out the values in the tree, we need a system for doing so.
In all cases, we will print out the left child before the right child. However,
that does not tell us when to print out the root node.

Consider this simple tree:
```
  2
 / \
1   3
```
- If we print it out in prefix notation, that means we print out the node value
    before the left child (and we always print out the left child before the
    right child). Thus, that tree would be printed as, “2 1 3”.
- If we print it out in infix notation, that means we print out the node value
    between (or in-between) the left and right child. Thus, that tree would be
    printed as, “1 2 3”.
- If we print it out in postfix notation, that means we print out the node value
    after the children (and always the left child before the right child). Thus,
    that tree would be printed as “1 3 2”.

In all cases, “printing a child” means recursively printing the entire sub-tree
contained underneath that child. For example, when we say to print the left
child before printing the right child, all the data contained at and under the
left child will be printed before anything contained at or under the right child
is printed.

Here is how to represent the first tree shown above:
```
Prefix: 1 2 4 5 3 6 7
Infix: 4 2 5 1 6 3 7
Postfix: 4 5 2 6 7 3 1
```

Here is how to represent the second tree shown above:
```
Prefix: 1 2 5 4 7 3 6
Infix: 2 4 5 7 1 3 6
Postfix: 4 7 5 2 6 3 1
```

Given a tree printed out in prefix and infix form, print it out in postfix form

## Description

### Input
The first line of the file will have an integer, n, which is the number of test
cases in this file.

Each test case will consist of three lines. The first line of a test case is a
number v, the number of vertices (nodes) in the tree. The second line is a list
of v integers that is the tree in prefix form. The third is a list of v integers
that is the tree in infix form.

Each test will have at most 1000 vertices. Each vertice will have a value
between 0 and 1000000

### Output
Each test case will have a single line in the output, with a space-separated
list of the tree vertex values in postfix form. It does not matter if there
is a trailing space on a line.

## Sample
### Input
```
2
7
1 2 4 5 3 6 7
4 2 5 1 6 3 7
7
1 2 5 4 7 3 6
2 4 5 7 1 3 6
```

### Output
```
4 5 2 6 7 3 1
4 7 5 2 6 3 1
```
