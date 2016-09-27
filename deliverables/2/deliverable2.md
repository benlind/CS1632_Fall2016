# CS 1632 - Software Quality Assurance
Fall Semester 2016  
DUE 11 OCT 2016  

## Deliverable 2

For this assignment, you (not a group) will write code and unit tests for CitySim9003.

Requirements for this program are in the requirements.txt file in this directory.  Sample output is also provided for several runs of the program.  In case of ambiguity, please see the sample output as an example of what to display and how the system should work.  Note that the sample output shows specific routes for given seeds - you do NOT have to have your seeds create the routes.  They are purely for demonstration purposes.

All code and tests should be on GitHub or GitLab in a private repository accessible to me.

## Format
You should turn in a title page with:
* Your name
* The URL of your code and tests on GitHub or GitLab
* The title "CS 1632 - DELIVERABLE 2: Unit Testing CitySim9003"

ENSURE THAT THE TA AND I ARE ADDED AS A COLLABORATOR AND CAN CLONE YOUR REPOSITORY!  My username is laboon on both GitHub and GitLab.  You will lose an automatic 10 points if I cannot access your repository.

Add a short ( < 1 page ) description of issues you faced when writing this code and tests.  If any tests you wrote fail, they should be included here, along with why you think that they are failing.

After this, ON A SEPARATE PAGE, include a screen shot of the executed unit tests.  Note that not all tests have to pass!  However, if a test doesn't pass, it should be included in the concerns section above.

There is no need to print out the code.  It should be on GitHub (or GitLab) BY THE BEGINNING OF CLASS.

At least three (3) unit tests should use test doubles and/or mocks.

At least three (3) unit tests should use stubbing of methods.

I expect unit tests for AT LEAST each public method that returns a value (excluding the main method), using a variety of assertions and looking at different failure modes and edge cases.  Keep in mind some of the things we learned when doing manual testing; you should be cognizant of equivalence classes, boundary values, etc. and focus on them.

The program should use appropriate object-oriented design.  Think of what objects could possibly exist to describe this world, and what methods they should Do not attempt to do this entirely with static methods and variables, without classes, etc.  It is possible but will make testing more difficult!

If you are not familiar with seeds for random number generators, recall that in the absence of external input, a computer can only generate data deterministically.  This seed will act as our "external input".  Please review the Java Random API for more details to ensure that you are using seeds correctly - https://docs.oracle.com/javase/7/docs/api/java/util/Random.html.  You may use Random or a different random number generator if you prefer.  However, running the program twice with the same seed should always produce the same output.

Before each test, add some comments (two or three sentences, on average) explaining what the test is checking.  For example...

```java
	// Two LLs with different sizes should never be equal.
	// Create two linked lists, both of which have the same value in the initial node,
	// but one has several more nodes. 
	// They should not be equal to each other.
		@Test
		public void testNotEqualsDiffSizes() {
			LinkedList<Integer> ll11 = new LinkedList<Integer>();
			LinkedList<Integer> ll_3elems = new LinkedList<Integer>();

			ll11.addToFront(new Node<Integer>(new Integer(1)));
			ll_3elems.addToFront(new Node<Integer>(new Integer(3)));
			ll_3elems.addToFront(new Node<Integer>(new Integer(2)));
			ll_3elems.addToFront(new Node<Integer>(new Integer(1)));

			assertFalse(ll_3elems.equals(ll11));
		}
```

## Grading
I remind you that grammar and good code count as well as functionality.  By good code, I mean -

No commented-out code unless there's an EXPLICIT reason, e.g.
```java
// I couldn't get this assertion to work, but instead used a different assertion, below
// assertEquals(foo, 3);
assertTrue(foo == 3);
```

Properly indented code, e.g.
```java
public void doSomething() {
    doStuff();
}
```
NOT
```java
public
  void
                     doSomething()
{ doStuff(); }
```

Don't misspell words or use bad grammar, in comments or summaries.

For this project, you should endeavour to get a good sampling of different equivalence classes and success/failure cases.

## Grading Breakdown
* Summary and Testing Concerns- 10%
* Screenshot of executed unit tests - 10%
* Program Code - 40%
* Test Code - 40%

Please feel free to email me or come to office hours to discuss any problems you have. 
 