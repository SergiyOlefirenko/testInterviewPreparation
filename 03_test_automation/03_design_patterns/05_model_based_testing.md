# Model-Based Testing (MBT)

MBT is a design pattern that involves creating a model of the SUT. The model is then used to generate TCs that can be executed automatically. This approach can help to identify potential defects in application by testing all possible combinations of inputs and outputs.

The goal is to test the system's behavior rather than its code, and to ensure that the system meets its requirements and behaves as intended.

The process of model-based testing usually involves the following steps:
1. Model creation: this can be a high-level abstract model or more detailed model that includes system behavior, inputs, and outputs.
2. Test case generation: The model is used to create TCs that exercise different scenarios and test the system's behavior.
3. Test execution.
4. Analysis of test results.

One of benefits of MBT is that it can help identify potential problems early in the development cycle. Additionaly, MBT can help to reduce the number of TCs needed to test a system, which can save time and resources.

MBT can be applied in various testing domains, such as functional testing, performance testing, and security testing. It can also be used in various types of systems, including embedded systems, web applications, and mobile applications.

---
<br/>

## MBT can be implemented in Python using various libraries

1. PyModel: it uses Finite State Machines (FSMs) to represent system behaviors and generates test cases based on different coverage criteria.
2. Hypothesis is a library for property-based testing. It allows you to  define properties that your SUT should satisfy and generates test cases automatically to verify those properties. Hypothesis uses an algorithmic approach to generate test cases that cover different edge cases and inputs.
3. ModelTester uses state machines to represent system behaviors and generates TCs based on different coverage criteria.
4. Robot Framework allows you to define test cases using a high-level, domain-specific language and generate test cases from model.