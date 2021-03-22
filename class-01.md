Ian Cooper TDD:

Its exciting to be getting deeper into the why and how of testing. It's all seemed ambiguous to me and I hadn't had any particular strategy in mind for navigating tests. With this new material it's a breath of fresh having some light shed on TDD. I can sure see how it's useful. I liked Ian's talk because he gave some history on TDD and did a good job further explaining the points from the book section reading. 
The test shouldn't be testing the implimentation steps taken it should be focused on outcomes. If the same thing is fed into the test it should always return the same value as well. As far as I'm understanding those two are the keys to tests. While writting the tests it's a good practice to make the test fail, pass and be able to refactor. 


Red Green Refactor:

Tests are meant to inform the implementation of a feature in TDD.
starting point is red phase where the test fails and will only pass when expectations are met. 
The green phase is the 2nd phase and it is where changes are made, however small and bad coding practice they may be, to get the test to pass.
Once you're in the green begin to look at the code and see if a refactor is possible to make the code more efficient, easier to read, etc. 

Cyclces of TDD:

 Three Laws of TDD (Nano Cycle)
- You must write a failing test before you write production code
- You must not write more of a test than is sufficient to fail, or fail to compile.
- You must not write more production code than is sufficient to make the currently failing test pass. 

The minute by minute (Micro Cycle, red green refactor)
This cycle is typically executed once for every complete unit test, or once every dozen or so cycles of the three laws. The rules of this cycle are simple.
Write a failing unit test
write production code making the test pass
Refactor the code into nicer code

Decaminute-by-Decaminute: (milli-cycle: Specific/Generic)
As the test suite grows it becomes more specific. To be a good developer we meet that with writing production code that is more and more generalized. Production code is likely too specific if it will make one test pass but future tests will require modifying the production code. The solution is to backtrack and then add specificity to the tests more slowly, while adding generality to the production code more quickly.
