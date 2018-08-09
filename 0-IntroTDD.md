# Introduction to Test Driven Development (TDD)

[source](http://www.agiledata.org/essays/tdd.html)

Test-driven development (TDD) (Beck 2003; Astels 2003), is an evolutionary approach to development which combines test-first development where you write a test before you write just enough production code to fulfill that test and [refactoring](http://www.agiledata.org/essays/databaseRefactoring.html).   What is the primary goal of TDD?  One view is the goal of TDD is specification and not validation (Martin, Newkirk, and Kess 2003).  In other words, it’s one way to think through your requirements or design before your write your functional code (implying that TDD is both an important [agile requirements](http://www.agilemodeling.com/essays/agileRequirements.htm) and [agile design](http://www.agilemodeling.com/essays/agileDesign.htm) technique). Another view is that TDD is a programming technique.  As Ron Jeffries likes to say, the goal of TDD is to write clean code that works. I think that there is merit in both arguments, although I lean towards the specification view, but I leave it for you to decide.

__Contents__

1. What is TDD?
2. TDD and traditional testing
3. TDD and documentation
4. Test-driven database development
5. Scaling TDD via Agile Model-Driven Development (AMDD)
6. Why TDD?
7. Myths and misconceptions
8. Who is actually doing this?
9. Summary
10. Tools

## 1. What is TDD?

![Test-Driven Database Development book](http://images.amazon.com/images/P/032178412X.01.MZZZZZZZ.jpg)

The steps of test first development (TFD) are overviewed in the UML activity diagram of Figure 1 below.

- The first step: is to quickly add a test, basically just enough code to fail.
- The second step: you run your tests, often the complete test suite although for sake of speed you may decide to run only a __subset__, to ensure that the new test does in fact fail.
- The third step: You then update your functional code to make it pass the new tests.
- The fourth step: is to run your tests again. If they fail you need to update your functional code and retest. Once the tests pass the next step is to start over (you may first need to `refactor` any duplication out of your design as needed, turning `TFD` into `TDD`).

![Figure 1. The steps of test-first development (TFD)](http://www.agiledata.org/images/tddSteps.jpg)

I like to describe TDD with this simple formula: $TDD = Refactoring + TFD$

TDD completely turns _traditional_ development around. When you:

- First go to __implement__ a new feature, the first question that you ask is whether the existing design is the _best_ design possible that enables you to implement that functionality.
- If so, you proceed via a __TFD approach__, if not, you refactor it locally to change the portion of the design affected by the new feature, enabling you to add that feature as easy as possible.
- As a result you will always be __improving the quality__ of your `design`, thereby making it easier to work with in the future.

Instead of writing `functional code` first and then your testing code as an afterthought, if you write it at all, you instead write your test code before your functional code. Furthermore, you do so in very small steps – one test and a small bit of corresponding functional code at a time.

A programmer taking a `TDD` approach refuses to write a new `function` until there is first a test that fails because that function __isn’t present__. In fact, they refuse to add even a single line of code until a `test` exists for it. Once the test is in place they then do the work required to ensure that the test suite now passes (your new code may break several existing tests as well as the new one).  This sounds simple in principle, but when you are first learning to take a TDD approach it proves require great discipline because it is easy to “slip” and write functional code without first writing a new test.  One of the advantages of [pair programming}(http://www.amazon.com/exec/obidos/ASIN/0201745763/ambysoftinc) is that your pair helps you to stay on track.
