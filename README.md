# LeetCode 114 - Flatten Binary Tree to Linked List

## Problem

Given the root of a binary tree, flatten the tree into a linked list **in-place**.

The linked list should use the same `TreeNode` structure, where:

* The `right` pointer points to the next node.
* The `left` pointer of every node must be `None`.
* The order of the nodes must follow the tree's **preorder traversal**.

Preorder traversal follows:

```text
Root → Left → Right
```

## Example 1

### Input

```text
root = [1,2,5,3,4,null,6]
```

### Output

```text
[1,null,2,null,3,null,4,null,5,null,6]
```

### Explanation

The original tree is:

```text
        1
       / \
      2   5
     / \   \
    3   4   6
```

Its preorder traversal is:

```text
1 → 2 → 3 → 4 → 5 → 6
```

After flattening, the tree becomes a linked list:

```text
1 → 2 → 3 → 4 → 5 → 6
```

All `left` pointers are set to `None`.

## Example 2

### Input

```text
root = []
```

### Output

```text
[]
```

## Example 3

### Input

```text
root = [0]
```

### Output

```text
[0]
```

## Approach

The required linked list must follow **preorder traversal**.

One efficient approach is to process each node and rearrange its pointers in-place.

For a node with a left subtree:

1. Find the rightmost node of the left subtree.
2. Connect that node to the current node's original right subtree.
3. Move the left subtree to the right.
4. Set the left pointer to `None`.
5. Continue with the new right child.

This rearranges the tree without creating a separate list of nodes.

## Algorithm

1. Start from the root.
2. While the current node exists:

   * If it has a left child:

     * Find the rightmost node of the left subtree.
     * Connect that node to the current right subtree.
     * Move the left subtree to the right.
     * Set the left pointer to `None`.
   * Move to the right child.
3. The resulting structure is the required linked list.

## Complexity

* **Time Complexity:** `O(n)` amortized.
* **Space Complexity:** `O(1)`.

The tree is modified in-place and no additional data structure is required.

## LeetCode Details

**Problem Number:** 114
**Problem Name:** Flatten Binary Tree to Linked List
**Difficulty:** Medium
**Topics:** Binary Tree, Depth-First Search, Linked List, In-Place

## Language

Python 3

## File

`solution.py`

## Author

T.Nandhini
