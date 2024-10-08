# CS605_Fall24_govardhan_baddala

#class
class represents a node in the binary search tree

value: A tuple with two elements, (name, phone_number), where the name is used for comparisons when inserting or searching.
left: A reference to the left child of the node.
right: A reference to the right child of the node

## class BSTNode:
    def __init__(self, value):
        self.value = value  
        self.left = None
        self.right = None
