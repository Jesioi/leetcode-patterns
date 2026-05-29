# Tree Construction DFS

Core Idea:
recursive function builds subtree from range

dfs returns:
constructed subtree root

Parent needs:
attach returned subtree to left/right child

Common Signals:

- construct tree
- build tree
- preorder + inorder
- inorder + postorder

Representative Problems:

- Construct Binary Tree from Preorder and Inorder
- Construct Binary Tree from Inorder and Postorder

## Example

```Java
// preorder + inorder
// dfs returns constructed subtree root

class Solution {
    int preIndex = 0;
    Map<Integer, Integer> map = new HashMap<>();

    public TreeNode buildTree(int[] preorder, int[] inorder) {

        for (int i = 0; i < inorder.length; i++) {
            map.put(inorder[i], i);
        }

        return build(preorder, 0, inorder.length - 1);
    }

    private TreeNode build(int[] preorder, int left, int right) {

        // subtree range empty
        if (left > right) return null;

        // preorder gives current root
        int rootVal = preorder[preIndex++];
        TreeNode root = new TreeNode(rootVal);

        // inorder splits subtree
        int mid = map.get(rootVal);

        root.left = build(preorder, left, mid - 1);
        root.right = build(preorder, mid + 1, right);

        return root;
    }
}
```

```Java
// sorted array -> balanced BST

class Solution {
    public TreeNode sortedArrayToBST(int[] nums) {
        return build(nums, 0, nums.length - 1);
    }

    private TreeNode build(int[] nums, int left, int right) {

        if (left > right) return null;

        int mid = left + (right - left) / 2;

        TreeNode root = new TreeNode(nums[mid]);

        root.left = build(nums, left, mid - 1);
        root.right = build(nums, mid + 1, right);

        return root;
    }
}
```
