# Optimal Binary Search Tree

## Procedure
- Creating the DP table:
  - this was by far the most difficult part. It really make me think hard about the prior elements of the table that I would need to complete each cell (and more importantly, how to translate these into the correct indicies).
- Re-building the tree:
  - rebuilding the tree was pretty simple, however, I believe it gave a lot of insight into the utility of the table and helpfulness of recursion.
- Printing the tree:
  - Since this wasn't necessarily part of the algorithm, I took some open source code to print the re-constructed trees. The link to that code can be foudn in my code comments, however, it can also be accessed [here](https://github.com/saibabanadh/print-bst/blob/master/bst.js).

## How to Run
- ```node index.js```

## Testing
For my initial two tests, they were chosen because they were examples that we went over in both the homework and recitation.

For additional testing, I used an example from stackoverflow that were pre-computed. That url can be found [here](https://stackoverflow.com/questions/46160969/generating-an-optimal-binary-search-tree-cormen). In addition, I used an example from a youtube video I found [here](https://www.youtube.com/watch?v=wAy6nDMPYAE). I decided to use pre-computed examples so that I could rule out my computation being incorrect (even if I were to do it on paper).

Although there were only four tests in total, having all inputs spit out correct solutions gave me a pretty good idea of the correctness of my algorithm.

## Conclusions
Though it ended up being a daunting task, I think that there was a lot to be learned with regard to both the *construction* of the dynamic programming table and the *rebuilding* of the tree.

The construction portion helped my solidify the intuition behind the algorithm and *why* all of these steps are necessary. Prior to coding it up, even after lecture and recitation, I still was extremely confused on how to find the optimal root. After coding up my incorrect implementation and doing more research, though, this became more clear and actually implementing it correctly solidified the algorithm in my mind.

As for the rebuilding of the tree, it gave me even more insight into the foundation of the dynamic programming table and how it can be used properly. In lecture and recitation we glossed over the actual reconstruction however I was curious how this would work in practice. The tree-rebuilding is also just a great example of a classic BST recursion. In addition, it also kind of coorelates with our talk of graph traversals as it is very similar to DFS in the way it builds the tree.

If I had more time maybe I would create a function that would de-construct a non-optimal BST and then re-construct it as optimal. I think that would be a pretty useful implementation of this algorithm.