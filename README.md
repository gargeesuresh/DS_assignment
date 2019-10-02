# DS_assignment
## Binary Tree Cameras 

Given a binary tree, we install cameras on the nodes of the tree. 

Each camera at a node can monitor its parent, itself, and its immediate children.

> Calculate the minimum number of cameras needed to monitor all nodes of the tree.


`
class Solution {

    int ans= 0;
    int  Cams(Node root) {
        int status = Find(root);
        if( state == 0 )
          return ans+1 ;
        return ans;
    }

   int helper(TreeNode root) {
        //(null case)
        if (root == null)
            return -1;

        //(leaf node case)
        if (root.left == null && root.right == null) 
            return 0;

        int leftState = Find(root.left), rightState = Find(root.right);

        //no camera, not seen,return 2
		    //if one of left or right child is no camera, not seen, then place a camera, return 2
        if (leftState == 0 || rightState == 0) {
            result++;
            return 2;
        }

       
		    //if two child are no camera, covered, or one child is null and other child is no camera, covered, then return 0
        if ((leftState == 1 || leftState == -1) && (rightState == 1 || rightState == -1))
            return 0;

        //other case
        return 1;
    }
}` 
