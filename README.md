# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of recursion (feel free to quote an official source like MDN)
* An example in code.
* An explanation of the code example.
* An explanation of the kinds of functions that are best solved using recursion.

### Response 1
Recursion is the act of a function calling itself---an intuitive approach when problems can be broken down into (more often) similar, but smaller subpbroblems.

The factorial is probably the easiest introduction that one could have at recursion. Let's see what that looks like in JS.

```JS
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n - 1);
}
```

Recursion is typically broken up into two: (1) the base case and (2) the recursive case. Base case is the stopping point, at which the problem cannot be broken down into smaller subproblems anymore.

In the factorial example above, this happens when we are looking for `0!`, which by default is equal to `1`. All other numbers after `0`, however, could be computed by multiplying the number itself by the factorial of the number before it. Below is a list of the first few factorials. Observe the trend.

```JS
0! = 1
1! = 1 * 0! = 1 * 1 = 1
2! = 2 * 1! = 2 * 1 = 2
3! = 3 * 2! = 3 * 2 = 6
```

The magic in recursion is when you realize that any further iterations of a given pattern depends or builds up on what is typically immediately before it. In the factorial's case, the factorial of `n` builds up on the factorial of `n-1`, and it goes on until the base case of `0!`. As for other problems involving recursion, a few examples would be the fibonacci sequence, and the towers of hanoi problem (very cool!).

## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of a Tree (feel free to quote an official source like MDN)
* Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
* An example in code.
* An explanation of the code example.

### Response 2

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

### Response 3

## Prompt 4

Depth-first-search is an algorithm of traversing through a tree that explores as far as possible along a single branch before backtracking and exploring other branches. The three approaches for depth-first-search are "inorder", "preorder", and "postorder".

Using this tree as an example, explain the differences between these three approaches, providing implementations of each (recursive or iterative, its up to you but one of them is definitely cleaner).

```
    A
   / \
  B   C
 / \   \
D   E   F
```

### Response 4

Depth-first search (DFS) explores a tree (or graph) by going as deep as possible along each branch before backtracking. The order in which the nodes are visited depends on the specific DFS approach:

- **Inorder:**  Visit the left subtree, then the root, then the right subtree. (Left, Root, Right)
- **Preorder:** Visit the root, then the left subtree, then the right subtree. (Root, Left, Right)
- **Postorder:** Visit the left subtree, then the right subtree, then the root. (Left, Right, Root)

Using the example tree:

```
    A
   / \
  B   C
 / \   \
D   E   F
```

The traversals would visit the nodes in the following orders:

- **Inorder:** D -> B -> E -> A -> C -> F
- **Preorder:** A -> B -> D -> E -> C -> F
- **Postorder:** D -> E -> B -> F -> C -> A

Then, to simulate this in JavaScript:

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.left = null;
    this.right = null;
  }
}

// we pass down a result variable in our traversals
// in order to compile the nodes and print it
// in one neat line.
const inorder = (node, result) => {
  if (node) {
    inorder(node.left, result);
    result.push(node.data);
    inorder(node.right, result);
  }
}

const preorder = (node, result) => {
  if (node) {
    result.push(node.data);
    preorder(node.left, result);
    preorder(node.right, result);
  }
}

const postorder = (node, result) => {
  if (node) {
    postorder(node.left, result);
    postorder(node.right, result);
    result.push(node.data);
  }
}

// creating the tree
const root = new Node("A");
root.left = new Node("B");
root.right = new Node("C");
root.left.left = new Node("D");
root.left.right = new Node("E");
root.right.right = new Node("F");

const inorderResult = [];
inorder(root, inorderResult);
console.log("Inorder traversal:", inorderResult.join(" -> "));

const preorderResult = [];
preorder(root, preorderResult);
console.log("Preorder traversal:", preorderResult.join(" -> "));

const postorderResult = [];
postorder(root, postorderResult);
console.log("Postorder traversal:", postorderResult.join(" -> "));
```

First, we define a simple `Node` class. This class is like a blueprint for creating each node in our tree. Each node holds some data, and it also has pointers to its left and right children.

Then we have three functions for traversing the tree: `inorder`, `preorder`, and `postorder`. The `inorder` function left->current->right. The `preorder` function visits current->left->right. The `postorder` function visits left->right->current.

Then we simulate the same tree from the example above. Try running the code yourself to see how it works!
