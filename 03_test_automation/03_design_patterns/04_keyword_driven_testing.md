# Keyword Driven Testing (KDT)


KDT is a type of test automation framework that uses a set of keywords to represent the actions and parameters required for each test case. This approach enables test automation engineers to write test cases in a way that is easy to read and understand, even by non-technical stakeholders.

The basic idea behind KDT is to separate the test case design from the test automation implementation. The test cases are designed using a set of keywords that represent the actions that need to be performed on the application or system under test, and the expected results. These keywords are then mapped to a set of automation scripts that perform the actual actions on the application.

The keyword-driven approach can be implemented in various wasy, but the basic steps involved the following:
1. Identify the keywords: a set of keywords should be defined that represent the actions required to test the application or SUT. These keywords should be simple and easy to understand.
2. Design the test cases: the TCs should be designed using the identified keywords. Each TC should include a set of keywords that represent the actions to be performed and the expected results.
3. Map the keywords to automation scripts: the keywords in each test case are mapped to a set of automation scripts that perform actual actions on the SUT. Each KW is mapped to a specific script of set of scripts that perform the required action.
4. Execute the tests: the TCs are executed using the mapped automation scripts.

---
<br/>

## Pros and Cons of KDT

**Advantages:**
1. Easy to understand
2. Reusability: the KWs and automation scripts can be used for different TCs, reducing the time and effor required for test automation.
3. Modularity: the keyword-driven approach enables test automation engineers to build modular test cases tath can be easily maintained and updated.
4. Scalability: KDT cab be easily scaled up to handle large and complex applications or systems.
5. Reduced maintenance: changes to SUT can be easily accommodated by updating the keywords, without affecting the automation scripts.

**Disadvantages:**
1. Requires more initial effort to design the KWs and map them to the automation scripts.
2. Complex mapping: the mapping of KWs to automation scripts can become complex and difficult to manage for large and complex applications or systems.
3. Requires technical expertise to design and implement the automation scripts, which may limit the involvement of non-technical stakeholders in the testing process.

---
<br/>

## Example

KDT using Robot framework

1. Crate a test suite: Create a new directory for your test suite and create a new file <mark>test_suite.robot</mark>. This file will contain your test cases and keywords.

2. Define the KWs that you will use in your test cases.
```
*** Keywords ***
Open Browser
    [Arguments]    ${url}
    Open Browser    ${url}    Chrome
```

3. Define test case:
```
*** Test Cases ***
Login
    Open Browser    https://example.com/login
    Input Text    id=username    johndoe
    Input Text    id=password    password123
    Click Button    id=login-button
    Wait Until Page Contains    Welcome, John Doe!
```

4. Run the test suite:
```
robot test_suite.robot
```
This will execute all the test cases in the test suite.