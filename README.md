# Optimal Binary Search Tree: Generation & Display

## Acknowledgements:
- I made use of a function, ```buildTree``` which was taken from [here](https://github.com/saibabanadh/print-bst/blob/master/bst.js). This function takes in the root of a binary tree and pretty-prints the tree to the console. I would have used the original package, [print-bst](https://www.npmjs.com/package/print-bst), however, it forces you to build the entire tree through the package (vs. just passing in a root).
- [test case #3](https://stackoverflow.com/questions/46160969/generating-an-optimal-binary-search-tree-cormen)
- [test case #4](https://www.youtube.com/watch?v=wAy6nDMPYA)

## How to Run:
- ```node index.js```

## Approach/Procedure:
- Creating the DP table:
  - this was by far the most difficult part. It really make me think hard about the prior elements of the table that I would need to complete each cell (and more importantly, how to translate these into the correct indicies).
- Re-building the tree:
  - rebuilding the tree was pretty simple, however, I believe it gave a lot of insight into the utility of the table and helpfulness of recursion.
- Printing the tree:
  - Since this wasn't necessarily part of the algorithm, as stated in the *acknowledgments* section, I took some open source code to print the re-constructed trees.

## Functions:
```js
const calc = (hitWeights, missWeights) => {}
```
Parameters:
- hitWeights
  - An array of integers. Each integer equal to the probability (weight) that that node with the ID equal to the index in this array will be queried.
- missWeights:
  - An array of integers. Each integer equal to the probability (weight) that there will be a query that falls in between hitWeights[i] and hitWeights[i + 1]

Example given a tree of 5 nodes: (h denotes a hitWeight and m denodes a missWeight):
- Ordered: { $m_0, h_1, m_1, h_2, m_2, h_3, m_3, h_4, m_4, h_5, m_5$ }
- Input: 
  - hitWeights: [$h_1$, $h_2$, $h_3$, $h_4$]
  - missWeights: [$m_0$, $m_2$, $m_3$, $m_4$, $m_5$]

Return value:
- A 2D array where each index is an object containing ```{ weight, cost, root }```

<br/>

```js
const generateOptimalTree = (nodeCount, startNode, endNode, data, hitWeights) => {}
```

Parameters:
- nodeCount
  - the amount of nodes our tree will contain
- startNode
  - the 'lowest' node our tree can contain.
- endNode
  - the 'highest' node our tree can contain
- data
  - our DP table generated in the ```calc()``` function
- hitWeights
  - The hitWeights from our input. This is used to map node weights to values for display.

Return value:
- A pointer to the root of an OBST generated from the input data

## Testing:
For my initial two tests, they were chosen because they were examples that we went over in both the homework and recitation.

For additional testing, I used an example from stackoverflow that was pre-computed. In addition, I used an example from a youtube video I found. I decided it was best to use pre-computed examples so that I could rule out my computation being incorrect (even if I were to do it on paper).

Although there were only four tests in total, having all inputs spit out correct solutions gave me a pretty good idea of the correctness of my algorithm.

## Conclusions:
Though it ended up being a daunting task, I think that there was a lot to be learned with regard to both the *construction* of the dynamic programming table and the *rebuilding* of the tree.

The construction portion helped my solidify the intuition behind the algorithm and *why* all of these steps are necessary. Prior to coding it up, even after lecture and recitation, I still was extremely confused on how to find the optimal root. After coding up my incorrect implementation and doing more research, though, this became more clear and actually implementing it correctly solidified the algorithm in my mind.

As for the rebuilding of the tree, it gave me even more insight into the foundation of the dynamic programming table and how it is be used properly. In lecture and recitation we glossed over the actual reconstruction however I was curious how this would work in practice. The tree-rebuilding itself is also a great example of a classic, somewhat elegant BST recursion. In addition, it also kind of coorelates with our talk of graph traversals as it is very similar to DFS in the way it builds the tree by exhausting the left sub-tree's before touching the right ones.

If I had more time I would probably create a function that would de-construct a non-optimal BST and then re-construct it as optimal. I think that would be a pretty useful implementation of this algorithm.