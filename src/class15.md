# Trees in Python 
Today I learned about trees and binary trees in Python. Trees are a fundamental data structure used to represent hierarchical relationships between elements. They consist of nodes connected by edges. Each node can have zero or more child nodes, except for the root node which has no parent.

Binary trees are a specific type of tree where each node can have at most two child nodes, commonly referred to as the left child and the right child. The left child is smaller than the parent node, while the right child is greater. This property makes binary trees useful for efficient searching and sorting operations.

In Python, we can implement trees and binary trees using classes and objects. Each node in the tree can be represented by a class that contains data and references to its left and right child nodes. We can define methods to insert new nodes, search for specific values, and traverse the tree in various ways, such as preorder, inorder, and postorder.

To create a binary tree in Python, we start by defining a Node class. Each node has a value and references to its left and right child nodes. We can then create methods within the Tree class to perform various operations on the binary tree.
# Trees terms:
- Root: The topmost node in a tree. It has no parent and serves as the starting point for traversing the tree.

- Parent: A node that has one or more child nodes. It is located above its child nodes in the tree.

- Child: Nodes directly connected to a parent node. A parent can have zero or more child nodes.

- Leaf: Nodes that have no child nodes. They are also known as external nodes or terminal nodes.

- Internal Node: Nodes that have at least one child node. They are located between the root and the leaf nodes.

- Sibling: Nodes that share the same parent. They are at the same level in the tree.

- Depth/Level: The depth or level of a node represents the number of edges from the root to that node. The root node is at level 0.

- Height: The height of a tree is the maximum depth among all the nodes in the tree. It represents the length of the longest path from the root to a leaf node.

- Subtree: A subtree is a smaller tree within a larger tree. It consists of a node and all its descendants.

- Binary Search Tree (BST): A binary tree in which the values are ordered or sorted. The left child of a node contains a value smaller than the node, while the right child contains a value greater than the node. BSTs are commonly used for efficient searching and sorting.


