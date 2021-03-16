##### 二叉搜索树的第k大节点  
***
> 只需要注意二叉搜索树的中序遍历是递增的，则中序遍历的倒序是递减的，中序遍历（左->根->右),倒序(右->根->左)  

```c++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
private:
    int k;
    int res;
public:
    int kthLargest(TreeNode* root, int k) {
        this->k = k;
        dfs(root);
        return res;
    }
    void dfs(TreeNode* root){
        if(!root)   return;
        dfs(root->right);
        if(k==0)    return;
        if(--k==0)  res=root->val;
        dfs(root->left);
    }
};
```
