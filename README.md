# leetcode145-postOrder


Iterative：
方法一：用反过来的preorder

    class Solution:
      def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
          stack = []
          res = []
          if root:
              stack.append(root)
          while stack:
              root = stack.pop()
              res.append(root.val)
              if root.left:
                  stack.append(root.left)
              if root.right:
                  stack.append(root.right)
                  
          return res[::-1]
          
          完全是preorder的方法，只是左右换了一下。最后再倒序一下
          
          
   
   
  方法三：recursive - 高级
  （开心哦，你也学会偷懒了）
  
        class Solution:
            def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
                if not root:
                    return []
                else:
                    return self.postorderTraversal(root.left) + self.postorderTraversal(root.right) + [root.val]

