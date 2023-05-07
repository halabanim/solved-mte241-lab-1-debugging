Download Link: https://assignmentchef.com/product/solved-mte241-lab-1-debugging
<br>
The purpose of this lab is to introduce you to techniques for debugging programs on embedded systems. After completing this lab, you should be able to:




<ul>

 <li>Identify and fix C syntax errors</li>

 <li>Understand and fix common compile time errors</li>

 <li>Identify code that does not conform to common C formatting standards and make the appropriate changes</li>

 <li>Use the debugger to</li>

</ul>

○    Watch local and global variables

○    Check the contents of memory

○    Set breakpoints

○   Step through code

<ul>

 <li>Correct logic errors</li>

</ul>




<h1>About the Project</h1>

In this lab, you’ll be debugging a program that uses binary search trees.

The binary search tree struct stores the address of the root node and the number of nodes currently stored in the tree. This is implemented using the bst_t structure, as defined in bst.h.




Every node within the tree stores the addresses of both the left and right children (NULL if there is no child there) as well as the integer value stored in this node (of type S32). This is implemented using the bst_n structure, as defined in bst.h.




The bst.c file implements the following functions (with some errors you will need to fix) to manipulate the binary search tree with <em>n</em>​ ​ nodes and a height <em>h</em>​ ​:

<strong>void bst_init( bst_t * ); </strong>

Initialize the binary search tree so that it is empty. Run time: <em>Θ</em>​ ​(1)




<strong>U32 bst_size(); </strong>

Return the number of nodes in the binary search tree. Run time: <em>Θ</em>​ ​(1)

<h1>bool bst_insert( bst_t *, S32 );</h1>

Insert the given integer into the binary search tree and return false if the node is already in the tree

(do not add a duplicate into the tree) and true otherwise. Run time: O(h)

<h1>S32 bst_min( bst_t * );</h1>

Returns the smallest integer in the binary search tree. Return

2

INT_MAX if the tree is empty. Run time: O(h)

<h1>S32 bst_max( bst_t * );</h1>

Returns the largest integer in the binary search tree. Return INT_MIN if the tree is empty. Run time: O(h)

<h1>bool bst_erase( bst_t *, S32 );</h1>

If the object is in the binary search tree, remove it and return true; otherwise, return false and do nothing. Run time: O(h)




While completing the various exercises, you are welcome to create other helper functions and you are welcome to add additional fields onto any of the records as you find necessary.




#include &lt;stdbool.h&gt; has been added to allow access to the type bool​ .​




#include &lt;limits.h&gt; is used to access INT_MIN ​ and ​ INT_MAX​ .​




Goals




Your goals in this lab are as follows:

<ol>

 <li>Fix the syntax errors so that the code compiles with 0 errors and 0 warnings.</li>

 <li>Improve the C formatting and style, and fill in the comments block at the top of bst.c to document what you changed.</li>

 <li>Fix the logic errors so the program produces the output shown below. There are four logic errors, but one of them (interestingly) has no impact on the results. Remember to fill in the comment block at the top of bst.c to document what you changed.</li>

</ol>

<strong>Expected output:</strong>

<table width="429">

 <tbody>

  <tr>

   <td width="196"></td>

   <td width="102">Min</td>

   <td width="131">Max</td>

  </tr>

  <tr>

   <td width="196">Before first group erased:</td>

   <td width="102">-3</td>

   <td width="131">9593</td>

  </tr>

  <tr>

   <td width="196">After first group erased:</td>

   <td width="102">-3</td>

   <td width="131">9593</td>

  </tr>

  <tr>

   <td width="196">After second group erased:</td>

   <td width="102">23</td>

   <td width="131">9593</td>

  </tr>

  <tr>

   <td width="196">After third group erased:</td>

   <td width="102">140</td>

   <td width="131">9593</td>

  </tr>

  <tr>

   <td width="196">After fourth group erased:</td>

   <td width="102">140</td>

   <td width="131">9265</td>

  </tr>

  <tr>

   <td width="196">After fifth group erased:</td>

   <td width="102">2147483647</td>

   <td width="131">-2147483648</td>

  </tr>

 </tbody>

</table>





