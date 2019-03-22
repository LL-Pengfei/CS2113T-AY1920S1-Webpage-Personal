**Questions to discuss during tutorial:** Divide these questions among team members. Be prepared to answer questions allocated to you.

**Q1**

1. What is _Liskov Substitution Principle_?<br>
   Give an example from the project where LSP is followed and explain how to change the code to break LSP.
1. Explain how _Law of Demeter_ affects coupling<br>
   a. Add a line to this code that violates LoD
   ```java
   void foo(P p){
       //...
   }
   ```
1. Give an example in the project code that violates the _Law of Demeter_.

**Q2**
1. Explain and justify: _testing should be efficient and effective_
1. Explain how _exploratory_ and _scripted_ testing is used in AB4/project
1. Give an example of a _negative_ test case in AB4/project
1. Explain _grey-box_ test case design

**Q3**
1. Explain: _Equivalence Partition_ improve E&E of testing
1. What are the EPs for the parameter `day` of this method
   ```java
   /**
    * Returns true if the three values represent a valid day
    */
   boolean isValidDay(int year, int month, int day){
   
   } 
   ```

**Q4**
1. Explain: _Boundary Value Analysis_ improves E&E of testing
1. What are the boundary values for the parameter `day` in the question above?
1. How can EP and BVA heuristics be used in AB4/project? Hint: See [[AB4 Learning Outcomes: LO-TestCaseDesignHeuristics]({{module_org}}/addressbook-level4/blob/master/docs/LearningOutcomes.adoc#apply-test-case-design-heuristics-code-lo-testcasedesignheuristics-code)]
1. How do you ensure some clean up code is run after each JUnit test case?

**Q5**

1. What is test coverage? How is it used in AB4?
1. How to measure coverage in Intellij?
1. What’s the difference between _validation_ and _verification_?<br>
   Acceptance tests are validation tests or verification tests?
1. Give an example of _static analysis_ being used in Intellij
