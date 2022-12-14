# Convert Sorted Array to Binary Search Tree
- ## Question:
>Given an integer array nums where the elements are sorted in ascending order, convert it to a height-balanced binary search tree.
>
>A height-balanced binary tree is a binary tree in which the depth of the two subtrees of every node never differs by more than one.

- Example :

      Input: nums = [-10,-3,0,5,9]
      Output: [0,-3,9,-10,null,5]
      Explanation: [0,-10,5,null,-3,null,9] 

- ## Solution:
```cpp
class Solution {
public:
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return helper(nums, 0, nums.size()-1);
    }
    TreeNode* helper(vector<int>& nums, int left, int right){
        if(left > right){
            return NULL;
        }
        int mid = (left + right) / 2;
        TreeNode* temp = new TreeNode(nums[mid]);
        temp->left = helper(nums, left, mid-1);
        temp->right = helper(nums, mid+1 , right);
        return temp;
    }
};
```
## Tags
`Array` `Divide conquer` 
