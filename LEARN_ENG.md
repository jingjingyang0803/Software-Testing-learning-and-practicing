# ✅ **1. INTRODUCTION TO SOFTWARE TESTING**

## **Q1. What is software testing and why is it important?**

**Answer:**

Software testing is the process of evaluating software to find defects and ensure it meets requirements.

**Importance:** improves quality, reduces risk, verifies functionality, increases reliability.

**Important concepts:**

- Testing = quality assurance, not just bug finding.
- Testing gives **confidence**, not proof.

**Common mistake:**

Thinking testing ensures **zero defects** — impossible.

---

## **Q2. Difference between defect, error, failure, bug?**

- **Error** → Human mistake (developer misunderstanding).
- **Defect/Bug** → Problem in the code.
- **Failure** → System behavior deviates from expected result.

**Common mistake:**

Confusing “error” and “defect.”

---

## **Q3. Objectives of software testing?**

- Find defects
- Gain confidence in product quality
- Verify requirements
- Prevent failures in production
- Improve product reliability

---

## **Q4. Why can't testing prove the absence of defects?**

Because you cannot test **all combinations** or scenarios.

**Important:**

Testing **reduces risk**, never eliminates it.

---

## **Q5. What is the “pesticide paradox”?**

Repeating the same tests will eventually fail to find new bugs.

**Solution:**

Update test cases regularly.

---

---

# ✅ **2. UNIT TESTING**

## **Q6. What is unit testing?**

Testing **smallest testable parts** (functions, components) in isolation.

---

## **Q7. Stub vs Mock?**

- **Stub:** Returns fixed values → simulates dependent modules.
- **Mock:** Verifies interactions → tracks calls, behavior.

**Error-prone point:**

Students often mix them up.

**Remember:** mock = verify behavior.

---

## **Q8. Popular unit testing frameworks?**

- JUnit
- pytest
- NUnit
- Jasmine / Jest for JS

---

## **Q9. What is TDD?**

Test-Driven Development = **Write tests first**, code second.

Steps:

1. Red (fail)
2. Green (pass)
3. Refactor

---

## **Q10. Why is unit testing commonly automated?**

- Fast
- Repeatable
- Consistent
- Easy integration with CI/CD

---

---

# ✅ **3. INTEGRATION TESTING**

## **Q11. What is integration testing?**

Testing how modules interact **after unit testing**.

---

## **Q12. Top-down vs Bottom-up?**

- **Top-down:** Test from top-level modules → use stubs.
- **Bottom-up:** Test from lower modules → use drivers.

---

## **Q13. What are drivers and stubs?**

- **Driver** → calls lower-level modules (used in bottom-up)
- **Stub** → dummy module (used in top-down)

---

## **Q14. Example where incremental integration is preferred?**

Large banking system → Big-bang too risky.

Incremental reduces debugging complexity.

---

## **Q15. What is hybrid integration?**

Combines top-down + bottom-up.

---

---

# ✅ **4. SYSTEM TESTING**

## **Q16. What is system testing?**

Testing the entire system end-to-end.

---

## **Q17. Types of non-functional tests?**

- Performance
- Security
- Usability
- Compatibility
- Reliability

---

## **Q18. Purpose of end-to-end testing?**

Simulate **real user workflows** across the whole application.

---

## **Q19. Why must system testing be production-like?**

To reflect actual runtime behavior.

---

## **Q20. What is configuration testing?**

Testing different configurations: browser versions, OS, hardware.

---

---

# ✅ **5. ACCEPTANCE TESTING**

## **Q21. What is acceptance testing?**

Final testing done by the **customer** to verify satisfaction.

---

## **Q22. Difference UAT vs Alpha?**

- **UAT (User Acceptance Test):** Done by real users.
- **Alpha:** Done internally before release.

---

## **Q23. What is beta testing?**

Released to external users for real-world feedback.

---

## **Q24. Why is acceptance testing done by client?**

Because only the client can validate business value and real needs.

---

## **Q25. Example of acceptance criterion?**

“User must be able to reset password within 1 minute.”

---

---

# ✅ **6. SOFTWARE PROCESS**

## **Q26. What is the V-model?**

Each development phase has a corresponding testing phase.

---

## **Q27. QA in Agile?**

- Continuous testing
- Tester participates in backlog, story refinement
- Test automation
- Pair testing with dev

---

## **Q28. Waterfall vs Agile testing?**

- **Waterfall:** Late testing, documentation-heavy
- **Agile:** Early testing, iterative, flexible

---

## **Q29. What is shift-left testing?**

Move testing earlier in development.

---

## **Q30. What is continuous testing?**

Testing integrated into CI/CD pipelines.

---

Great! Continuing with the same clean structure:

✔ **Clear answers**

✔ **Important concepts**

✔ **Common error-prone points**

---

# ✅ **7. TEST CASES**

## **Q31. What is a test case?**

**Answer:**

A set of conditions, inputs, execution steps, and expected results used to verify specific behavior.

**Essential components:**

- Test case ID
- Title
- Pre-conditions
- Test steps
- Test data
- Expected result
- Actual result (executed later)
- Status

**Error-prone point:**

Beginners forget *preconditions* and *test data.*

---

## **Q32. What is a test suite?**

A collection of test cases grouped by functionality (e.g., Login Test Suite).

---

## **Q33. What is a test scenario?**

A high-level description of what to test, without step-by-step details.

Example: “Verify user can log in successfully.”

---

## **Q34. Example of a test case for a login page.**

- **Title:** Login with valid credentials
- **Steps:**
    1. Enter valid email
    2. Enter valid password
    3. Click Login
- **Expected:** Redirect to home page

---

## **Q35. Expected result vs Actual result?**

- **Expected:** What should happen ideally
- **Actual:** What happened during execution

---

**Important concepts:**

- Test cases must be **clear**, **repeatable**, and **unambiguous**.
- Good test cases don’t depend on each other.

---

# ✅ **8. TEST CASE DESIGN TECHNIQUES**

## **Q36. What is equivalence partitioning?**

Divide inputs into groups where all values behave the same.

Example: Age field 1–120 → partition:

- Invalid: <1
- Valid: 1–120
- Invalid: >120

---

## **Q37. What is boundary value analysis?**

Test values at the edges:

If 1–120 is valid → test:

- 0
- 1
- 120
- 121

**Error-prone point:**

Students forget **just-beyond** values.

---

## **Q38. What is decision table testing?**

A testing method using a table of rules and outcomes, especially for complex business logic.

---

## **Q39. State transition testing?**

Tests how the system behaves when moving between states.

Example:

ATM

- State: “Card inserted” → “PIN entered.”

---

## **Q40. What is pairwise testing?**

Test all combinations of input pairs rather than full combinations.

Useful when input combinations explode (e.g., 7 parameters).

---

### Important concepts

- **Black-box techniques:** EP, BVA, decision tables, state transitions, pairwise.
- **White-box techniques:** Code coverage, path testing.

---

### Error-prone points

- Forgetting invalid states.
- Testing only happy path, not negative cases.

---

# ✅ **9. EXPLORATORY TESTING**

## **Q41. What is exploratory testing?**

Simultaneous learning, test design, and execution without predefined scripts.

---

## **Q42. Difference from scripted testing?**

- Scripted = Pre-written test cases
- Exploratory = Tester decides during testing

---

## **Q43. What is a test charter?**

A mission or goal for an exploratory session.

Example:

“Explore the login page for usability issues.”

---

## **Q44. Skills important for exploratory testers?**

- Critical thinking
- Domain knowledge
- Creativity
- Observation
- Curiosity

---

## **Q45. What is Session-Based Test Management?**

A structured approach to exploratory testing with:

- Time-boxed sessions
- Goals
- Notes
- Debriefing

---

**Error-prone misunderstanding:**

Exploratory ≠ random testing. It is structured and purposeful.

---

# ✅ **10. DYNAMIC TESTING**

## **Q46. What is dynamic testing?**

Testing by executing code.

---

## **Q47. Black-box vs white-box testing?**

- **Black-box:** No knowledge of internal code → focus on inputs/outputs
- **White-box:** Requires code knowledge → focus on paths, conditions

---

## **Q48. What is code coverage?**

Measures which lines/branches of code were executed during tests.

Types:

- Line coverage
- Branch coverage
- Path coverage

---

## **Q49. What is performance testing?**

Testing speed, responsiveness, stability under load.

Types:

- Load testing
- Stress testing
- Soak testing
- Spike testing

---

## **Q50. Example of dynamic testing in mobile apps?**

Testing navigation, gestures, network requests, battery usage.

---

**Important concept:**

Dynamic testing ALWAYS runs the software; static testing does not.

---

### Error-prone points

- Confusing stress testing with load testing
- Thinking high coverage = high quality (not always)

---

# ✅ **11. RISK ANALYSIS**

## **Q51. What is risk-based testing?**

Prioritizing tests based on risk (likelihood × impact).

---

## **Q52. Difference between project risk and product risk?**

- **Project risk:** Schedule, resources, budget
- **Product risk:** Functional, performance, security risks in the product

---

## **Q53. Likelihood vs impact?**

- **Likelihood:** How likely something will fail
- **Impact:** How big the damage if it fails

---

## **Q54. Example of high-risk feature?**

Payment processing → Very high impact and medium likelihood.

---

## **Q55. What is risk mitigation?**

Actions taken to reduce risk.

Example: Add automated tests for core features.

---

**Error-prone point:**

Risk = not only “probability,” but also **severity**.

---

Great! Here are **Topics 12–19**, with:

✔ Clear answers

✔ Important concepts

✔ Error-prone points / misunderstandings

This completes the **full study set**.

---

# ✅ **12. MEASURING (Metrics)**

## **Q56. What are software testing metrics?**

**Answer:**

Quantitative measures used to assess testing progress, quality, and effectiveness.

Examples:

- Number of test cases executed
- Test coverage
- Defect density
- Defect severity distribution

---

## **Q57. What is defect density?**

Defects per size of software, e.g.:

[

\text{Defect density} = \frac{\text{Number of defects}}{\text{KLOC or Function Points}}

]

---

## **Q58. What is test coverage?**

How much of the software is covered by tests (code or requirements).

---

## **Q59. What is the defect leakage metric?**

Measures defects missed in testing and found by customers.

[

\text{Leakage} = \frac{\text{Defects found after release}}{\text{Total defects}}

]

---

## **Q60. What is test effectiveness?**

How efficiently tests detect defects.

---

### **Important concepts**

- Metrics must be **meaningful**, not just numbers.
- High coverage ≠ high quality.

### **Error-prone points**

- Misusing metrics to “judge tester performance.”
- Confusing defect density with defect severity.

---

# ✅ **13. TEST AUTOMATION**

## **Q61. What is test automation?**

Using tools/scripts to run tests automatically instead of manual execution.

---

## **Q62. Why automate tests?**

- Faster feedback
- Repeatability
- Cost-effective long-term
- Supports CI/CD
- Reduces human error

---

## **Q63. What types of tests should be automated?**

- Regression tests
- Smoke tests
- API tests
- Repetitive tasks

**Avoid automating:** one-time or UI-heavy unstable tests.

---

## **Q64. What is a test automation framework?**

A structured environment that supports automation, e.g.:

- Selenium
- Cypress
- Playwright
- Robot Framework
- JUnit

---

## **Q65. What is the ROI of automation?**

Return on investment = Benefits > Cost (tools + maintenance).

---

### **Error-prone points**

- Believing automation can replace manual testing.
- Automating everything (not practical).
- Underestimating maintenance cost.

---

# ✅ **14. MODEL-BASED TESTING (MBT)**

## **Q66. What is model-based testing?**

Tests are generated automatically from **models** (state machines, flowcharts, UML).

---

## **Q67. What is a model in MBT?**

A formal representation of system behavior, e.g.:

- State-transition model
- Activity diagrams
- Flowcharts
- Decision tables

---

## **Q68. Benefits of MBT?**

- Faster test generation
- Better coverage
- Less human error
- Easier to maintain with requirement changes

---

## **Q69. What is a state machine model?**

A model representing system states and transitions triggered by events.

---

## **Q70. Example where MBT is useful.**

ATM or elevator systems — many states and transitions.

---

### **Error-prone points**

- Confusing MBT with exploratory testing.
- Thinking MBT is only for automation (manual tests also possible).

---

# ✅ **15. AI TESTING**

## **Q71. What is AI testing?**

Using AI technologies to:

- Improve test automation
- Generate test cases
- Detect anomalies
- Predict defects

---

## **Q72. Difference between “AI for testing” and “testing AI”?**

- **AI for testing:** Using AI to enhance testing (e.g., object recognition in UI automation).
- **Testing AI:** Ensuring AI models behave correctly (accuracy, bias, robustness).

---

## **Q73. What special challenges exist when testing AI systems?**

- Non-deterministic outputs
- Continual learning
- Bias in data
- Explainability issues

---

## **Q74. What is model drift?**

AI accuracy decreases over time when real-world data changes.

---

## **Q75. What is adversarial testing?**

Feeding misleading input to trick AI (e.g., images with noise).

---

### **Error-prone points**

- Assuming traditional pass/fail tests fit AI.
- Ignoring data quality during AI testing.

---

# ✅ **16. DOCUMENTATION**

## **Q76. What are common testing documents?**

- Test plan
- Test strategy
- Test cases
- Test reports
- Traceability matrix

---

## **Q77. What is a test plan?**

A document describing **approach, scope, schedule, resources, and risks** of testing.

---

## **Q78. What is a test strategy?**

High-level approach: what to test, how to test, tools used.

---

## **Q79. What is a traceability matrix?**

Links requirements → test cases → defects.

---

## **Q80. What is a test report?**

Summary of testing activities, coverage, findings, recommendations.

---

### **Error-prone points**

- Confusing *test plan* (project-specific) vs *test strategy* (organization-level).
- Forgetting to update documentation when requirements change.

---

# ✅ **17. ERROR REPORTS / DEFECT REPORTING**

## **Q81. What is a defect report?**

A document describing a discovered defect with steps, expected vs actual, environment, severity.

---

## **Q82. Key fields in a defect report?**

- Title
- Description
- Steps to reproduce
- Expected vs actual result
- Severity
- Priority
- Environment
- Attachments/logs

---

## **Q83. Severity vs Priority?**

- **Severity:** How serious the defect is
- **Priority:** How quickly to fix it

Example:

- High severity, low priority → Crash in a rarely used feature.

---

## **Q84. What is “Cannot Reproduce” status?**

Tester reports a bug, but developer can't reproduce due to missing steps/environment mismatch.

---

## **Q85. What is root cause analysis (RCA)?**

Finding the underlying reason a defect occurred.

---

### **Error-prone points**

- Mixing severity and priority
- Poor reproduction steps → delays in fixing

---

# ✅ **18. STATIC TESTING**

## **Q86. What is static testing?**

Testing without executing code.

Includes:

- Reviews
- Walkthroughs
- Inspections
- Static analysis tools

---

## **Q87. Benefits of static testing?**

- Detect defects early
- Cheap to fix
- Improve code quality
- Prevent logic errors

---

## **Q88. What is code review?**

Developers inspect others’ code for defects, readability, adherence to standards.

---

## **Q89. What is static analysis?**

Automated tools check code for issues (SonarQube, ESLint, Pylint).

---

## **Q90. Example of static testing catching bugs early.**

Uninitialized variables, unused imports, unreachable code.

---

### **Error-prone points**

- Thinking static testing replaces dynamic testing
- Believing static tools catch all logic errors

---

# ✅ **19. SECURITY TESTING**

## **Q91. What is security testing?**

Testing to ensure software protects data and prevents attacks.

---

## **Q92. Common types of security testing?**

- Vulnerability scanning
- Penetration testing
- Authentication testing
- Authorization testing
- SQL injection testing
- XSS testing
- CSRF testing

---

## **Q93. What is SQL injection?**

Attacker inserts malicious SQL via input fields to manipulate the database.

---

## **Q94. What is XSS (cross-site scripting)?**

Injecting malicious JavaScript into webpages.

---

## **Q95. What is penetration testing?**

Simulated cyberattack to identify vulnerabilities.

---

## **Q96. What is authentication vs authorization?**

- **Authentication:** Who are you? (login)
- **Authorization:** What can you access? (permissions)

---

## **Q97. What is CSRF?**

Cross-Site Request Forgery → attacker tricks user into performing unwanted actions.

---

## **Q98. What is brute-force attack testing?**

Checking system resilience against repeated password attempts.

---

## **Q99. What is encryption testing?**

Verify sensitive data is stored and transmitted securely.

---

## **Q100. Example of security misconfiguration.**

Default admin password not changed.

---

### **Error-prone points**

- Confusing authentication & authorization
- Thinking HTTPS alone = secure
- Forgetting to test logout/session timeout
- Not testing password reset flows

---

Here is a **clean, concise, exam-ready one-page summary sheet** covering **all 19 topics**.

You can **copy this into a PDF**, or I can generate a formatted PDF version if you'd like.

---

# **Summary Sheet**

## ✅ **1. Introduction**

- Testing = evaluating software to find defects + ensure it meets requirements.
- **Error:** human mistake → **Defect/Bug:** in code → **Failure:** wrong system behavior.
- Testing reduces risk but **cannot prove zero defects**.
- **Pesticide paradox:** update test cases regularly.

---

## ✅ **2. Unit Testing**

- Tests smallest modules (functions/classes).
- Automated, fast, used in CI/CD.
- **Stub:** fake called module.
- **Mock:** verifies interactions.
- TDD cycle: Red → Green → Refactor.

---

## ✅ **3. Integration Testing**

- Tests interactions between modules.
- **Top-down:** uses stubs; **Bottom-up:** uses drivers.
- Incremental > Big-bang for large systems.

---

## ✅ **4. System Testing**

- Entire system tested end-to-end.
- Include functional + non-functional (performance, usability, security).
- Done on production-like environment.

---

## ✅ **5. Acceptance Testing**

- Validates system against business requirements.
- **UAT:** real users; **Alpha:** internal; **Beta:** external users.
- Based on acceptance criteria.

---

## ✅ **6. Software Process**

- **V-Model:** verification ↔ validation.
- **Agile:** continuous testing, shift-left.
- CI/CD → continuous testing.

---

## ✅ **7. Test Cases**

- Components: ID, title, steps, input, expected result, preconditions.
- Test suite = group of test cases.
- Test scenario = high-level user flow.

---

## ✅ **8. Test Case Design**

- **Equivalence Partitioning (EP)**: valid/invalid groups.
- **Boundary Value Analysis (BVA)**: edges (min−1, min, max, max+1).
- **Decision table:** complex logic.
- **State transition:** state-based behavior.
- **Pairwise:** input combination reduction.

---

## ✅ **9. Exploratory Testing**

- Simultaneous learning + design + execution.
- Uses **test charters** and **session-based testing**.
- Purposeful, not random.

---

## ✅ **10. Dynamic Testing**

- Running the code.
- **Black-box:** input/output; **White-box:** internal structure.
- Coverage: line, branch, path.
- Includes performance testing.

---

## ✅ **11. Risk Analysis**

- Risk = **likelihood × impact**.
- **Product risks:** defects in software.
- **Project risks:** schedule, resources.
- Risk-based testing → prioritize critical areas.

---

## ✅ **12. Measuring**

- **Defect density** = defects/KLOC.
- **Coverage:** requirement or code.
- **Defect leakage:** found post-release.
- Metrics show progress, not tester performance.

---

## ✅ **13. Test Automation**

- Best for regression, smoke, API tests.
- Not all tests should be automated.
- Frameworks: Selenium, Cypress, Playwright.
- High maintenance cost → manage wisely.

---

## ✅ **14. Model-Based Testing**

- Automatically generates tests from models.
- Models: state machines, flowcharts, UML.
- Good for complex systems (ATM, elevator).

---

## ✅ **15. AI Testing**

- **AI for testing:** AI improves automation.
- **Testing AI:** validate ML model accuracy, bias, robustness.
- Challenges: non-determinism, model drift, bias.

---

## ✅ **16. Documentation**

- Documents: Test Plan, Test Strategy, Test Cases, Traceability Matrix, Test Report.
- Test plan = project-level; test strategy = organization-level.
- Traceability links requirements → test cases → defects.

---

## ✅ **17. Error / Defect Reporting**

- Defect report fields: steps, expected/actual, severity, priority, environment.
- **Severity:** impact; **Priority:** urgency.
- RCA = find cause of bug.

---

## ✅ **18. Static Testing**

- Without execution: reviews, walkthroughs, inspections, static analysis tools.
- Early defect detection → cheaper fixes.
- Tools: SonarQube, ESLint, Pylint.

---

## ✅ **19. Security Testing**

- Checks protection against attacks.
- Test SQL injection, XSS, CSRF, authentication/authorization.
- Penetration testing simulates attacks.
- Validate encryption, session handling, brute-force protections.

---

# **Critical Concepts**

- BVA & EP
- Severity vs Priority
- Types of testing (unit → integration → system → acceptance)
- Static vs dynamic testing
- Test case structure
- Risk = likelihood × impact
- Automation ROI
- Code coverage types
- Authentication vs authorization
- Alpha vs beta vs UAT

---
