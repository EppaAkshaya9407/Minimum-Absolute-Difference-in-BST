# Minimum-Absolute-Difference-in-BST
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def getMinimumDifference(self, root: Optional[TreeNode]) -> int:
        r=[]
        def add(root,r):
            if root is None:
                return 
            add(root.left,r)
            r.append(root.val)
            add(root.right,r)
        add(root,r)
        a=float('inf')
        for i in range(1,len(r)):
            a=min(a,abs(r[i]-r[i-1]))
        return a
