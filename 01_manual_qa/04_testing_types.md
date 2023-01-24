# Testing Types


## Functional Testing

Functional testing verifies that each function of the SW application operates in conformance with the requirement specification. Functional testing tends to answer the questions like "can the user do this" or "does this particular feature work". This is typically described in a requirements specification or in a functional specification.

***Testing functionality can be done from two perspectives:***
- Requirement-based testing is performed in strict accordance with the defined requirements.
- Business-process-based testing is performed in accordance with the knowledge on the day-to-day business use of the system.

***Functional testing advantages:***
- Functional testing simulates actual system usage.
- It is executed in the conditions close to the customer's ones.
- No system structure assumptions are made while providing functional testing.

***Functional testing limitations:***
- There is high possibility of redundant testing.
- Logical errors in SW could be missed while providing functional testing.


## Non-functional testing types

Non-functional refers to aspects of the system that may not be related to a specific function or user action such as scalability or security. Eg. how many people can log in at once? Non-functional testing is also performed at all levels like functional testing.

Non-functional testing includes:
- **Performance testing** is performed to determine how fast some aspect of a system performs under a particular workload. It can serve different purposes like it can demonstrate that the system meets performance criteria. It can measure what part of the system or workload causes the system to perform badly.
- **Load testing** is usually conducted to understand the behavior of the application under a specific expected load. It is performed to determine a system's behavior under both normal and at peak conditions. It helps to identify the maximum operating capacity of an application as well as any bottlenecks and determine which element is causing degradation.
- **Stress testing** involves testing beyond normal operational capacity, often to a breaking point, in order to observe the results. It put greater emphasis on robustness, availability, and error handling under a heavy load, rather than on what would be considered correct behavior under normal circumstances. The goal of such tests may be to ensure the SW does not crash in conditions of insufficien computational resources.
- **Volume testing** regers to testing a SW application or the product with a certain amount of data.
- **Endurance testing** involves testing a system with a significant load extended over a significant period of time, to discover how the system behaves under sustained use.
- **Installation testing**
- **Usability testing**
- **Failover and recovery testing**
- **Configuration testing**
- **Security testing** to check that whether the application or the product is secured or not.
- **Localization testing** 



## Changes related testing types

### \#1. Smoke testing
The purpose of smoke testing is to determine whether the build SW is testable or not. It is done at the time of "building SW". It is a time-saving process. It reduces testing time becasue testing is done only when the key features of the app are not working or if the key bug are not fixed. The focus of Smoke Testing is on the workflow of the core and primary functions of the app. Testing the basic and critical features of an app before doing one round of deep, rigorous testing.

### \#2. Regression testing
It is used to verify that a code change in the SW does not impact the existing functionality of the product. Regression testing is making sure that the product works fine with new functionality, bug fixes, or any change in the existing feature. Regression testing can be performed on a new build when there is a significant change in the original functionality. It ensures that the code still works even when the changes are occuring. Regression means re-test those parts of app, which are unchanged.

### \#3. Re-testing
Re-testing is a procedure where we need to check that particular test cases which are found with some bugs during the execution time. Re-testing also occurs when the product is already tested due to some problems it needs to be tested again.

### \#4. Sanity testing
Sanity testing is a subset of regression testing. Sanity testing is a kind of Software Testing performed after receiving a software build, with minor changes in code, or functionality, to ascertain that the bugs have been fixed and no further issues are introduced due to these changes. The goal is to determine that the proposed functionality works roughly as expected. If sanity test fails, the build is rejected to save the time and costs involved in a more rigorous testing.