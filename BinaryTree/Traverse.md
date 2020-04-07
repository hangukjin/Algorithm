Default
```
def traverse(node, lst):
    if node:
        lst.append(node)
        traverse(node.left, lst)
        traverse(node.right, lst)

def getTargetCopy(self, original: TreeNode, cloned: TreeNode, target: TreeNode) -> TreeNode:
    original_list = []
    cloned_list = []
    traverse(original, original_list)
    traverse(cloned, cloned_list)

    for n1, n2 in zip(original_list, cloned_list):
            if n1 == target:
                return n2
```



Generator
```python
class Solution:
    def getTargetCopy(self, original: TreeNode, cloned: TreeNode, target: TreeNode) -> TreeNode:
        def it(node):
            if node:
				yield node
				yield from it(node.left)
				yield from it(node.right)
            
        for n1, n2 in zip(it(original), it(cloned)):
            if n1 == target:
                return n2
```