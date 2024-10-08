# CS605_Fall24_govardhan_baddala
```
1. class

class represents a node in the binary search tree
value - tuple with two elements (name, phone_number)
left - left child of the node.
right - right child of the node

class BSTNode:
    def __init__(self, value):
        self.value = value  
        self.left = None
        self.right = None


2. Binary Search Tree


The tree starts with no nodes so the root is set to None

    a. Tree Initialization - __init__

   class BinarySearchTree:
   def __init__(self):
        self.root = None

    b. Insert

The insert takes a name and a phone_number and calls (_insert) with the root node and the tuple (name, phone_number)

    def insert(self, name, phone_number):
        value = (name, phone_number)  
        self.root = self._insert(self.root, value)

If the current node is None, it creates a new BSTNode with the value (name, phone_number) then it compares the new value with the current node value
If the new value is smaller it inserts into the left subtree otherwise it inserts into the right subtree.

    def _insert(self, node, value):
        if node is None:
            return BSTNode(value)
        if value < node.value:
            node.left = self._insert(node.left, value)
        else:
            node.right = self._insert(node.right, value)
        return node




    c. Search

The search method calls the method (_search) to look for a node with the matching name if it's found it returns the phone number (value[1]) otherwise it returns (Name not found)

    def search(self, name):
        node = self._search(self.root, name)
        if node:
            return node.value[1]
        else:
            return "Name not found"


If the node is None or the name matches return the node
If the name is smaller search in the left subtree
If the name is larger search in the right subtree

    def _search(self, node, name):
        if node is None or node.value[0] == name:
            return node
        if name < node.value[0]:
            return self._search(node.left, name)
        return self._search(node.right, name)


    d.  In-order Traversal

In-order traversal of the tree (left-root-right)

    def inorder_traversal(self):
        result = []
        def inorder(node):
            if node:
                inorder(node.left)
                result.append(node.value)
                inorder(node.right)
        inorder(self.root)
        return result

it collects and returns all node values (name and phone number) in sorted order


```
