## Testing Types

### Functional Testing
Functional testing verifies that each function of the SW application operates in conformance with the requirement specification. Functional testing tends to answer the questions like "can the user do this" or "does this particular feature work". This is typically described in a requirements specification or in a functional specification.

*Testing functionality can be done from two perspectives:*
- Requirement-based testing is performed in strict accordance with the defined requirements.
- Business-process-based testing is performed in accordance with the knowledge on the day-to-day business use of the system.

*Functional testing advantages:*
- Functional testing simulates actual system usage.
- It is executed in the conditions close to the customer's ones.
- No system structure assumptions are made while providing functional testing.

*Functional testing limitations:*
- There is high possibility of redundant testing.
- Logical errors in SW could be missed while providing functional testing.

<br>

### Non-functional testing types
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

<br>

### Changes related testing types
***\#1. Smoke testing***
***\#2. Regression testing***
***\#3. Re-testing***
***\#4. Sanity testing***