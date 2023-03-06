https://smartbear.com/learn/automated-testing/what-is-automated-testing/
https://www.globalapptesting.com/blog/what-is-automation-testing


# What is Automated Testing?

Automation testing is a SW testing technique to test and compare outcome with the expected outcome. This can be achieved by writing test scripts or using any automation testing tool. Test automation is used to automate repetitive tasks and other testing tasks with are difficult to perform manually.

The fundamental difference between manual and automated testing is straightforward. With manual testing, a human is responsible for single-handedly testing the functionality of the SW in the way a user would. Automated testing is done through an automation tool, so more time can be spent on higher value tasks, such as exploratory tests while automating time-consuming tests, such as regression tests. While you do need spend time maintaining test scripts overall, you will increase your test coverage and scalability.

The benefit of manual testing is that it allows a human mind to draw insights from a test that might otherwise be missed by test automation. Automated testing is well-suited for large projects, projects that require testing the same areas over and over, and projects that have already been through an initial manual testing process.

<hr>

## Implementing a Test Automation Strategy

The move to agile led many teams to adopt a pyramid testing strategy. The test automation pyramid strategy calls for automating tests at three different levels. Unit testing represents the base and biggest percentage of this test automation pyramid. Next comes, service layer, or API testing. And finally, UI tests sit at the top.

![Test Pyramid](../00_resources/01_img/test_automation/testPyramid.png)

From a modern point of view the test pyramid seems overly simplistic and can therefore be misleading. Still, due to its simplicity the essence of the test pyramid servers as a good rule of thumb when it comes to establishing your own test suite. Your best bet is to remember two things:

1. Write tests with different granularity.
2. The more high-level you get the fewer tests you should have.

<hr>

## What are the benefits of automation testing?

- **Reduces cost** - Automated SW testing will save money, resources, and time during the quality assurance process. SW tests have to be repeated often during development cycles to ensure quality. Every time source code is modified SW tests should be repeated. For each relase of the SW it may be tested on all supported operating systems and HW configurations. Manually repeating these tests is costly and time consuming. Once created, automated tests can be run over and over again at no additional cost and they are must faster than manual tests. Automated SW testing can reduce time to run repetitive tests from days to hours. A time savings that translates directly inot cost savings.

- **Vastly increase your test coverage** - Automated SW testing can increase the depth and scope of tests to help improve SW quality. Lengthy tests that are often avoided during manual testing can be run unattended. They can even be run on multiple computers with different configurations. Automated SW testing can look inside an application and see memory contents, data tables, file contents, and internal program states to determine if the product is behaving as expected. Test automation can easily execute thousands of different complex test cases during every test run providing coverage that is impossible with manual tests.

- **Testing improves accuracy** - Even the most conscientious tester will make mistakes during monotonous manual testing. Automated tests perform the same steps precisely every time they are executed and never forget to record detailed results. Testers freed from repetitive manual tests have more time to create new automated software tests and deal with complex features.

- **Automation does what manual testing cannot** - Even the largest software and QA departments cannot perform a controlled web application test with thousands of users. Automated testing can simulate tens, hundreds, or thousands of virtual users interacting with a network, software and web applications.

- **Automation testing helps developers and testers** - Shared automated tests can be used by developers to catch problems quickly before sending to QA. Tests can run automatically whenever source code changes are checked in and notify the team or the developer if they fail. Features like these save developers time and increase their confidence.

- **Run tests simultaneously** - Because automated testing requires little to no human input once it's started, you can run many tests at once. This also gives you the opportunity to make detailed comparative reports in less time with the same parameters.

- **Faster feedback cycle** - With manual tests, it can be a time-consuming process for testers to get back with feedback. Using test automation tools, you can execute faster validation during the development of your software. By testing early on, you increase your team's efficiency.

- **Faster time to market** - The time you save with continuous testing during development means that you'll be able to launch your product sooner. Automation testing tools can also get test results faster, expediting final software validation.

<hr>

## Tests that should be automated

1. Tests that need to be **run against every build/release of the application**, such as the smoke test, sanity test, and regression test.
2. Tests that **utilize the same workflow but different data** for its inputs for each test run (data-driven and boundary tests).
3. Tests that need to **gather multiple information during runtime**, like SQL queries and low-level application attributes.
4. Tests that can be **used for performance testing**, like stress and load tests.
5. Test that **take a long time to perform** may need to be run during breaks or vernight. Automating tests maximizes the use of time.
6. Some tests involve **inputting large volumes of data**.
7. Tests that need to **run against multiple configurations** - different OS & browser combinations, for example.
8. Test during which **images must be captured to prove that the application behaved as expected**.

<hr>

## Tests that should not be automated

1. **User experience tests for usability** - tests that require a user to respond as to how easy the app is to use.
2. Tests that you will only **run one time**.
3. Test that needs to **run ASAP**.
4. Tests that **require ad hoc/random testing based on domain or subject matter expertise/knowlede. Tests without predictable results**. For automation validation to be successful, it needs to have predictable results in order to produce pass-and-fail conditions.
5. If a test needs to be **manualy "eyeballed"** to determine whether the results are correct.
6. **Tests that cannot be 100% automated should not be automated at all** - unless doing so will save considerable time.
7. Test that **adds no value**.
8. Test that **doesn't focus on the risk areas** of your application.

---

## Concept of test automation framework

A test automation framework is as set of guildelines, rules, and coding standards that are used to develop automated tests in a consistent and scalable way.

Test automation frameworks provide a systematic approach to designing, writing, executing, and maintaining automated tests. They provide a structure for organizing test code and help ensure that tests are reliable, maintainable, and reusable.

A typical test automation framework consists of three main components:
1. Test library: this component contains a set of pre-defined functions or methods that can be used to automate specific actions, such as filling out a form, clicking a button, or verifying a piece of text.
2. Test runner: this component is responsible for executing the automated tests in a specific order and generating test reports.
3. Test data: contains input data and expected results for each test scenario.

There are serveral types of test automation frameworks, including keyword-driven, data-driven, behavior-driven, hybrid frameworks, and others.