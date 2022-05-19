# Chapter 09: Unit Tests

The three laws of Test Driven Development: 
1. You may not write production code until you have written a failing unit test.
2. You may not write more of a unit test than is sufficient to fail, and not compiling is failing.
3. You may not write more production code than is sufficient to pass the currently failing test.
- The issue with this is that the bulk of tests can rival the size of the production code itself.

Keeping Tests Clean:

- Issue: Modifying production code makes old tests fail and become a liability.
- Test code is just as important as production code, and must be kept clean so it is more easily editable when production code changes.
- Make test code readable: clear, simple, and expression density should be considered.

5 Rules of Clean Tests:
1. Fast: Incentive to run them frequently.
2. Independent: Should not depend on other tests.
3. Repeatable: Can run in any environment.
4. Self-Validating: Boolean output (pass or fail).
5. Timely: Written just before the production code that makes them pass.
