# DS_assignment
## Binary Tree Cameras 

Given a binary tree, we install cameras on the nodes of the tree. 

Each camera at a node can monitor its parent, itself, and its immediate children.

> Calculate the minimum number of cameras needed to monitor all nodes of the tree.


`class Solution{
    int ans= 0;
    int  Cams(Node root) 
    {
        int status = Find(root);
        if( state == 0 )
          return ans+1 ;
        return ans;
    }
   int   Find(Node root)
   {
       
        if (root == null)
            return -1;
        if (root.left == null && root.right == null) 
            return 0;
        int leftState = Find(root.left);
	int rightState = Find(root.right); 
        if (leftState == 0 || rightState == 0) 
	{
            result++;
            return 2;
        }
       if ((leftState == 1 || leftState == -1) && (rightState == 1 || rightState == -1))
            return 0;
        return 1;}}` 
