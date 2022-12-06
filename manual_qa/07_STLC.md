http://tryqa.com/what-is-software-testing-life-cycle-stlc/#STLC_Life_cycle


### Software Testing Life Cycle
STLC is the sequence of activities carried out by the testing team from the beginning of the project till the end of the project.

***STLC Phases***
1. **Requirement Analysis.** In this phase testing team goes through the requirement document with both functional and non-functional details in order to identify the testable requirements. Once the QA team is clear with the requirements they will document the acceptance criteria and get it approved by the customer.
    - *Activities:*
        - analyzing the SRS from the testing point of view.
        - preparation of Requirement Traceability Matrix.
        - identifying the testing techniques and testing types.
        - prioritizing the feature which need focused testing.
        - analyzing the automation feasibility.
        - identifying the details about the teting env where actual testing will be done.
    - *Deliverables:*
        - requirement traceability matrix (RTM).
        - automation feasibility report.
<br>

2. **Test Planing.** In this phase the QA manager and QA lead will prepare the Test Plan and Test Strategy documents. As per these documents they will also come up with the testing effort estimations.
    - *Activities:*
        - estimation of testing effort.
        - selection of testing approach.
        - preparation of test plan, test strategy documents.
        - resource planning and assigning roles and responsibility to them.
        - selection of testing tools.
    - *Deliverables:*
        - test plan document.
        - test strategy document.
        - best suited testing approach.
        - number of resources, skills required, their roles, and responsibility.
<br>

3. **Test Case Development.** In this phase the QA team write test cases. They also write scripts for automation if required. Verification of both test cases and test scripts are done by peers. Creation of test data is done in this phase.
    - *Activities:*
        - creation of test cases.
        - creation of test scripts if required.
        - verification of test cases and automation scripts.
        - creation of test data in testing environment.
    - *Deliverables:*
        - test cases.
        - test scripts (for automation if required).
        - test data.
<br>

4. **Environment Setup.** This phase icludes the setup or installation process of SW and HW which is required for testing the application. In this phase the integration of the third party application is also carried out if required in the project. After setting up tet env the installation of build is tested. Once the installation of build is successful and complete then the test data is generated. This phase can be done in parallel with the test case development phase.
    - *Activities:*
        - as per the requirement and architecture documents the list of required SW and HW is prepared.
        - setting up of test env.
        - creation of test data.
        - installation of build and execution of smoke testing on it.
    - *Deliverables:*
        - test environment setup is ready.
        - test data is created.
        - results of smoke testing.
<br>

5. **Test Execution.** In this phase the TCs are executed in the test env. While execution of the TCs the QA team may find bugs which will be reported against corresponding TC. This bug is fixed by the developer and is retested by the QA.
    - *Activities:*
        - TCs execution.
        - reporting test results.
        - logging defects for the failed test cases.
        - verification and retesting of the defects.
        - closure of defects.
    - *Deliverables:*
        - test execution report.
        - updated test cases with results.
        - bug report.
<br>

6. **Test Cycle Closure.** In this phase the QA team will meet and discuss about the tesing artifacts. The whole intent of this discussion is to learn lessons from the bad practices. This will help in future projects.
    - *Activities:*
        - to evaluate the test completion on the basis of test coverage and SW quality.
        - documentation of the learning from the project.
        - analyzing the test results to find out the distribution of severe defects.
        - test closure report preparation.
    - *Deliverables:*
        - report of test closure