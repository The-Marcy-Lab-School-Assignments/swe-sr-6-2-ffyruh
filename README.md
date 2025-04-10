# Technical Writing Assignment

For guidance on setting up and submitting this assignment, refer to the Marcy lab School Docs How-To guide for [Working with Short Response and Coding Assignments](https://marcylabschool.gitbook.io/marcy-lab-school-docs/fullstack-curriculum/how-tos/working-with-assignments#how-to-work-on-assignments).

## Prompt 1

Imagine you are giving a brief lesson on Recursion to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of recursion (feel free to quote an official source like MDN)
* An example in code.
* An explanation of the code example.
* An explanation of the kinds of functions that are best solved using recursion.

### Response 1

## Prompt 2

Imagine you are giving a brief lesson on the Tree data structure to a relatively new programmer. In your lesson make sure to include the following:

* A formal definition of a Tree (feel free to quote an official source like MDN)
* Definitions for key terms like **root**, **leaf**, **depth**, and **height** as they relate to Trees
* An example in code.
* An explanation of the code example.

### Response 2

A tree data structure is basically linked nodes (or data) that are connected to one another the same way a tree is. If you turn the data structure upside down it seems like a tree. Think of the tree bark as the root, the main head of the structure and the leaf are other nodes that don't have anything connecting to them, the same way a leaf doesnt have anything else hanging on it. From root to leaf ends that would be considered the height of the tree. Using the example below node j has a height of 3 because a -> c -> g -> j.  On the other hand depth is how many nodes in we have to go in so if we use a -> c -> g -> j as an example again our depth would be 3 as well. (we start depth at 0)

<!-- 

                                a
                             (root)
                    /                    \
                b                         c
            (parent/ child one)        (parent/ child two)
            /             \                    /        \
            d             e                  f           g
          (parent)     (leaf)              (leaf)        (parent)
            /                                                \
            h                                                j      
         (leaf)                                              (leaf)

 -->

## Prompt 3

Any iterative function can be written recursively. Provide an example of an iterative function and the same function written recursively. Then, explain the benefits and/or drawbacks of each approach.

### Response 3
An iterative function is anything that uses a loop (for or while loop). It is usually what we are taught from the beginning but as we learn anything we can iterate through we can do recursively. A recursive function invokes itself to start and continue. The benefits of doing a recursive function is the fact that it reduces time complexity, makes it easier to read and reduces the time we need to write out the code. With all of the advantages there are disadvantages like the fact it uses more memory, it can work slower than a normal loop and we can get stuck in the loop if we don't get out of it correctly.


```js 
            //iterative function
       const triangle = () => { 
        for (let i=0; i < 3; i++){
            console.log(i)
            } else if (i === 3){
                }
                console.log('end')
        }

        //recursion function
       const triangleSum = (i = 0) => {
        if (i === 3) {
                return (`end`); 
            } else {
                console.log (i)
                triangleSum(i++)
            }
        }
```


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
