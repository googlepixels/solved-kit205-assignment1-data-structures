Download Link: https://assignmentchef.com/product/solved-kit205-assignment1-data-structures
<br>
You work for an education company that develops and runs Massive Open Online Courses (MOOCs).  You have been asked to develop some software to manage student enrolments.  You decide to develop a prototype solution to test the performance of different data structures and algorithms.

The company will initially only offer a few courses, but that may expand significantly in the future.  More importantly, each course may have many thousands of students – perhaps even hundreds of thousands.  Your software needs to provide the following functions:

<ol>

 <li>Add a student</li>

 <li>Remove a student</li>

 <li>Enrol student in a course</li>

 <li>Un-enrol student from a course</li>

 <li>Print a summary of courses and the number of students enrolled in each course</li>

 <li>Print an ordered list of students enrolled in a course</li>

 <li>Print a list of courses that a given student is enrolled in</li>

</ol>

The number of courses that any student will enrol in is small.  Furthermore, there is no inherent order to the courses, so an ordered data structure is not required.  Therefore you decide to use a simple linked list to store the courses for each student.

The number of students will potentially be very large and, for quick access, sorted data is required.   Initially, you decide to test performance of a binary search tree to store the students, but you would like to test an AVL tree as well.  Note that, for this preliminary testing, only the student ids will be stored (as long ints).

<h2>Assignment Specification – Part A (</h2>

For this part of the assignment you will implement a prototype that uses BST to store students, with each student record containing a list of courses the student is enrolled in.  You must use the BST and linked list code developed in the tutorials, however the data structures will be modified for the new data (and functions will also require minor modifications to accommodate these changes).  The following definitions <strong>MUST</strong> be used:

typedef struct listNode{    char *data;

struct listNode *next;

} *ListNodePtr;

typedef struct list {

ListNodePtr head;

} List;




typedef struct bstNode {

long data;

List courses;        struct bstNode *left;

struct bstNode *right;

} *BSTNodePtr;

typedef struct bst {

BSTNodePtr root;

} BST;

The ListNodePtr and List definitions and (modified) linked list functions must be placed in files stringlist.h and stringlist.c.  The BSTNodePtr and BST definitions and (modified) BST functions must be placed in files bst.h and bst.c.

All remaining code should be placed in a file called main.c that contains the main function and program logic.  This file will contain separate functions for each of the seven operations listed in the introduction, as well as an eighth function to handle termination.  Other functions may be added if required.

<h3>Program I/O</h3>

All interactions with the program will be via the console.  Operations 1-7 will be selected by typing 1-7 at the command prompt.  Quitting the application will be selected by typing 0.  For example, the following input sequence would add a student with id 123456, enrol that student in course “abc123”, and then quit the application:

1

123456 3 123456 abc123 0

Note that this sequence shows the input only, not the program response (if any).  You are free to add prompts to make the application more user friendly, but this will not be assessed (although it may be useful).

Program output in response to operations 5-7, should be as minimal as possible.  You may print a header if you wish, but this should be followed by one record per line with spaces separating data.  For example, in response to operation 5, the output might be:

Current enrolments:

abc123 32  def456 0 123def 10236

<h3>I/O Restrictions</h3>

You may assume that all input will always be in the correct format and contain no logical errors.

<ul>

 <li>Commands will always be in the range 0-7</li>

 <li>Course names will always be strings less than 100 characters long and may contain any alpha-numeric characters <strong>excluding spaces</strong></li>

 <li>Student ids will always be positive integers in the range 0-999999</li>

 <li>The user will never attempt to add a student to a non-existent course</li>

 <li>The user will never attempt to print data for a non-existent course</li>

 <li>The user will never attempt to print data for a non-existent student</li>

</ul>

Note: Students that are enrolled in courses may be removed, in which case the course data for that student should also be removed

<h3>Memory Management</h3>

Course names should be stored in appropriately size dynamically allocated memory.  Names will always be less than 100 characters long.  For example, the course name “abc123” would be stored in a char string of length 7.

Removing (un-enrolling) a student or removing a course should free all associated dynamically allocated memory.  Removing a course should free all memory for the enrolled students as well as the course.  The quit function should also free all dynamically allocated memory.

<h2>Assignment Specification – Part B</h2>

This part of the assignment should only be attempted once you have a fully implemented <strong>and thoroughly tested</strong> solution to part A.  It would be better to submit a complete part A and no part B than to submit a partially complete part A and part B.

The requirements for this part of the assignment are exactly the same as for part A except that an AVL tree must be used to store students, rather than storing them in a BST.  The AVL files should be named avl.h and avl.c.  The AVL node definition should be a modified version of the BST node.

Minimal assistance will be provided for this part of the assignment, especially if you cannot demonstrate a fully implemented and thoroughly tested solution to part A.

<h2>Testing</h2>

It can be very time consuming to thoroughly test a program like this when all input is done manually (imagine testing that your solution can manage 10000 students).  A common method of testing code like this is to use input redirection (and possibly output redirection).  When using input redirection your code runs without modification, but all input comes from a file instead of from the keyboard.

This facility is provided in Visual Studio through the project properties dialog.  For example, to redirect input from a file called “test.txt”, you would add:

&lt;“$(ProjectDir)test.txt”

to <em>Configuration Properties|Debugging|Command Arguments</em>.  This will be demonstrated in tutorials.

At least one small input test file with sample output will be provided.  It is recommended that you construct larger files to fully test your program.