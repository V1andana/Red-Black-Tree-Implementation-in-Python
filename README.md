# Red-Black-Tree-Implementation-in-Python
A Red-Black Tree is a self-balancing Binary Search Tree in which each node is assigned either a red or black color. The tree maintains its balance through rotations and recoloring after insertion and deletion operations.
Concept:
A Red-Black Tree is a self-balancing Binary Search Tree in which each node is assigned either
a red or black color. The tree maintains its balance through rotations and recoloring after
insertion and deletion operations.
1. Aim
To implement a Red-Black Tree in Python with a menu-driven program supporting the
following operations:
1. Creation of a Red-Black Tree
2. Insertion of nodes
3. Deletion of nodes
4. Display of the tree
5. Exit
2. Algorithm
Creation of a Red-Black Tree
1. Start the program.
2. Create an empty Red-Black Tree by initializing the root to a special NIL sentinel node.
3. Assign the NIL sentinel node the color black. This node represents all missing
children.
4. Display the menu containing the following options:
o Creation
o Insertion
o Deletion
o Display
o Exit
5. When the user selects the Creation option:
o Initialize a new empty Red-Black Tree.
o Read a sequence of integer elements separated by spaces.
o For each element, perform the insertion operation.

o Check whether the element already exists in the tree. If it exists, display a
duplicate-value message and skip the insertion.
o Otherwise, insert the element according to the Binary Search Tree property.
o Restore the Red-Black Tree properties using recoloring and rotations, if
required.

6. Display a message indicating that tree creation is completed.
7. Return to the main menu.
Insertion of a Node
1. Start the insertion operation.
2. Read the integer value to be inserted from the user.
3. Search the tree to determine whether the value already exists.
4. If the value is present, display a message indicating that duplicate values are not
allowed and terminate the insertion operation.
5. Otherwise, create a new node containing the given value.
6. Initialize the new node as follows:
o Set its color to red.
o Set its left and right children to NIL.
o Set its parent pointer to NIL.
7. Traverse the tree from the root to find the appropriate insertion position:
o If the new value is smaller than the current node&#39;s value, move to the left
child.
o If the new value is greater than the current node&#39;s value, move to the right
child.
o Continue until a NIL position is reached.
8. Insert the new node at the identified position and update its parent pointer.
9. If the new node becomes the root, color it black.
10. Otherwise, check whether the parent of the newly inserted node is red.
11. If the parent is black, the Red-Black Tree properties are satisfied, and no further
adjustment is required.
12. If the parent is red, examine the node&#39;s uncle and apply the following cases.

Case 1: The uncle is red
 Change the parent color to black.
 Change the uncle color to black.
 Change the grandparent color to red.
 Continue checking from the grandparent because the violation may have moved
upward.
Case 2: The uncle is black and the node forms a triangle
 If the parent is the left child of the grandparent and the new node is the right child of
its parent, perform a left rotation on the parent.
 If the parent is the right child of the grandparent and the new node is the left child of
its parent, perform a right rotation on the parent.
 This converts the configuration into a straight-line arrangement.
Case 3: The uncle is black and the node forms a straight line
 Recolor the parent black.
 Recolor the grandparent red.
 If the configuration is left-left, perform a right rotation on the grandparent.
 If the configuration is right-right, perform a left rotation on the grandparent.
13. Repeat the adjustment process until the parent of the current node is black or the
root is reached.
14. Ensure that the root is black.
15. Display a message indicating successful insertion.
16. Stop the insertion operation.
Deletion of a Node
1. Start the deletion operation.
2. Read the integer value of the node to be deleted.
3. Search the Red-Black Tree for the specified value.
4. If the node is not found, display the message &quot;Node not found&quot; and terminate the
deletion operation.
5. Otherwise, identify the node to be deleted and record its original color.

6. Perform deletion according to the number of children.
Case 1: The node has no children
 Replace the node with its NIL sentinel child.
 Update the parent pointer accordingly.
Case 2: The node has only one child
 Replace the node with its existing child.
 Update the parent pointer of the replacement node.
Case 3: The node has two children
 Find the in-order successor, which is the smallest node in the right subtree.
 Record the original color of the successor.
 Replace the successor with its right child at its original position.
 Move the successor into the position of the node being deleted.
 Attach the deleted node&#39;s left and right subtrees to the successor.
 Assign the deleted node&#39;s color to the successor.
7. Check the original color of the physically removed node:
o If it was red, the black-height property remains unchanged, so no deletion fix-
up is required.
o If it was black, perform the deletion fix-up procedure to restore the Red-Black
Tree properties.

8. During deletion fix-up, consider the replacement node, its parent, and its sibling.
Apply the following cases.
Case 1: The sibling is red
 Recolor the sibling black.
 Recolor the parent red.
 Perform a rotation around the parent toward the replacement node.
 Update the sibling reference.
Case 2: The sibling and both of its children are black
 Recolor the sibling red, provided it is not the NIL sentinel.
 Move the replacement node upward to its parent.

 Continue the fix-up process.
Case 3: The sibling is black, the sibling&#39;s near child is red, and its far child is black
 Recolor the near child black.
 Recolor the sibling red.
 Perform a rotation around the sibling.
 Update the sibling reference to convert the configuration into Case 4.
Case 4: The sibling is black and its far child is red
 Assign the sibling the parent&#39;s color.
 Recolor the parent black.
 Recolor the sibling&#39;s far child black.
 Perform a rotation around the parent.
 Set the replacement node to the root to terminate the fix-up process.
9. Ensure that the replacement node is black after the fix-up process.
10. Ensure that the root remains black.
11. Display a message indicating successful deletion.
12. Stop the deletion operation.
Display of the Red-Black Tree
1. Start the display operation.
2. Check whether the root points to the NIL sentinel node.
3. If the root is NIL, display the message &quot;The tree is empty&quot; and terminate the display
operation.
4. Otherwise, display the root node&#39;s value and color.
5. Recursively display the left subtree:
o Move to the left child.
o Display its value and color with appropriate indentation.
o Label the node as a left child.
o Continue recursively until a NIL sentinel node is reached.
6. Recursively display the right subtree:

o Move to the right child.
o Display its value and color with appropriate indentation.
o Label the node as a right child.
o Continue recursively until a NIL sentinel node is reached.
7. Use R to represent red nodes and B to represent black nodes.
8. Return to the main menu.
Exit
1. Start the exit operation.
2. Display the message &quot;Exiting the program&quot;.
3. Terminate the menu loop.
4. Stop the program.
Main Menu
1. Initialize a Red-Black Tree object.
2. Display the menu options:
o 1 – Creation
o 2 – Insertion
o 3 – Deletion
o 4 – Display
o 5 – Exit
3. Read the user&#39;s choice.
4. Execute the corresponding operation:
o If the choice is 1, create a new tree and insert the initial elements.
o If the choice is 2, read a value and insert it into the existing tree.
o If the choice is 3, read a value and delete it from the existing tree.
o If the choice is 4, display the tree structure.
o If the choice is 5, terminate the program.
5. If the choice is outside the range 1 to 5, display an invalid-choice message.
6. If the user enters invalid integer input, display an error message.

7. Repeat Steps 2–6 until the user selects Exit.
8. Stop the program.

Sample Input &amp; Output:
===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 4

Red-Black Tree (R = Red, B = Black):
Root: 20 (B)
L--- 10 (B)
R--- 15 (R)
R--- 30 (B)

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 2
Enter the value to insert: 25
Node inserted successfully.

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 3
Enter the value to delete: 15
Node deleted successfully.

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 4

Red-Black Tree (R = Red, B = Black):
Root: 20 (B)
L--- 10 (B)
R--- 30 (B)
L--- 25 (R)

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion

4. Display
5. Exit
Enter your choice: 5
Exiting the program.

4. Sample Output
===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 1
Enter initial elements separated by spaces: 10 20 30 15
Node inserted successfully.
Node inserted successfully.
Node inserted successfully.
Node inserted successfully.
Tree creation completed.

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 4

Red-Black Tree (R = Red, B = Black):
Root: 20 (B)
L--- 10 (B)
R--- 15 (R)
R--- 30 (B)

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 2
Enter the value to insert: 25
Node inserted successfully.

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 3
Enter the value to delete: 15
Node deleted successfully.

===== RED-BLACK TREE MENU =====

1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 4

Red-Black Tree (R = Red, B = Black):
Root: 20 (B)
L--- 10 (B)
R--- 30 (B)
L--- 25 (R)

===== RED-BLACK TREE MENU =====
1. Creation
2. Insertion
3. Deletion
4. Display
5. Exit
Enter your choice: 5
Exiting the program.

Time Complexity
Operation Time Complexity
Creation of nodes O(nlog n)
Insertion O(nlog n)
Deletion O(nlog n)

Search O(nlog n)
Display O(n)
Space complexity O(n)

5. Result
Thus, the menu-driven Python program for implementing a Red-Black Tree was developed
and executed successfully. The program supports creation, insertion, deletion, and display
operations while maintaining the Red-Black Tree properties through appropriate rotations
and recoloring. The exit option terminates the program.
