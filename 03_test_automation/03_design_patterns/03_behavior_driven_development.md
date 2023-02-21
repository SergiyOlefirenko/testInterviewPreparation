# Behavior Driven Development (BDD)


BBD is a design pattern that focuses on the behavior of the application under test. BDD tests are written in a language that is easily understandable by all stakeholders, including business users, developers, and testers.


## Python has several libraries that support BDD, including:
- **Behave**. It uses Gherkin syntax to describe thes scenarios.

Example:
1. Define the behavior in a file called <mark>addition.feature</mark>. This file should be created under <mark>features</mark> directory.
```gherkin
Feature: Addition

  Scenario: Add two numbers
    Given I have the numbers 2 and 3
    When I add the numbers
    Then the result should be 5
```

2. Write the step definitions that implement the behavior described in the Gherkin scenario. In a file called <mark>step_definitions.py</mark> under <mark>features/steps<mark> directory.
```python
from behave import given, when, then
from behave_bdd.my_module import add


@given('I have the numbers {num1:d} and {num2:d}')
def step_impl(context, num1, num2):
    context.num1 = num1
    context.num2 = num2

@when('I add the numbers')
def step_impl(context):
    context.result = add(context.num1, context.num2)

@then('the result should be {result:d}')
def step_impl(context, result):
    assert context.result == result
```

3. Run the test with the command: ```behave features/addition.feature```.

```sh
Feature: Addition # behave_bdd/features/addition.feature:1

  Scenario: Add two numbers          # behave_bdd/features/addition.feature:3
    Given I have the numbers 2 and 3 # behave_bdd/features/steps/step_definitions.py:5 0.000s
    When I add the numbers           # behave_bdd/features/steps/step_definitions.py:10 0.000s
    Then the result should be 5      # behave_bdd/features/steps/step_definitions.py:14 0.000s

1 feature passed, 0 failed, 0 skipped
1 scenario passed, 0 failed, 0 skipped
3 steps passed, 0 failed, 0 skipped, 0 undefined
Took 0m0.001s
```

Project structure:
```
├── features
│   ├── addition.feature
│   └── steps
│       └── step_definitions.py
└── my_module.py
```

---

- **PyTest-BDD** is a plugin for the PyTest testing framework that allows write BDD-style tests using Gherkin syntax. Provides a set of tools to help you write clear and consise tests.

Example:
1. Define the behavior in a file called <mark>calculator.feature</mark>:
```gherkin
Feature: Calculator
    Simple calculator tests

    Scenario: Add two numbers
        Given I have entered 2 into the calculator
        And I have entered 3 into the calculator
        When I press add
        Then the result should be 5 on the screen
```

2. Write step definitors that implement the behavior described in the Gherkin scenario in a file <mark>test_calculator.py</mark>.
```python
from pytest_bdd import given, when, scenario, then, parsers

import pytest
from calculator import Calculator

@pytest.fixture
def calculator():
    return Calculator()

@given(
    parsers.cfparse('I have entered {number} into the calculator'))
def enter_number(calculator, number):
    calculator.enter(int(number))

@when('I press add')
def press_add(calculator):
    calculator.add()

@then(
    parsers.cfparse('the result should be {result} on the screen'))
def result_on_screen(calculator, result):
    assert calculator.result() == int(result)
```

3. Write the tests that use the step definitions to verify the behavior of the SUT. We can write in the same file <mark>test_calculator.py</mark>

```python
from pytest_bdd import given, when, scenario, then, parsers

@scenario('calculator.feature', 'Add two numbers')
def test_add_two_numbers():
    pass
```

Project structure:
```
├── calculator.feature
├── conftest.py
└── test_calculator.py
```

---
- **Lettuce** - supports a wide range of web testing frameworks, uses Gherkin systax. <mark>NOT SUPPORTED BY PYTHON 3.</mark>

---
<br>

## Pros and Cons of BDD

**Advantages:**
- Focus on business value: BDD emphasizes the importance of understanding and delivering business value, rather than just focusing on technical details.
- Collaboration: BDD encourages collaboration between developers, testers, product owners, and other stakeholders. By working together to define and verify the behavior of the system, BDD helps to ensure that everyone is on the same page and that the system is tested from mulitple perspectives.
- Traceability: BDD scenarios provide traceability between the business requirements, the behavior being tested, and the code that implements that behavior. This helps to ensure that the SW being developed meets the business requirements and that any changes made to the code are properly tracked.

**Disadvantages:**
- Complex tooling: BDD testing frameworks can be complex to set up and use, which can require additional training and expertise.
- Limited scope: BDD is primary focused on testing the behavior of the system, which may not cover all aspects of the SW.
- Time-consuming: BDD can be a time-consuming, as it requires collaboration among stakeholders to define the behavior of the system and translate it into scenarios. This can slow down the development process, especially if there are many stakeholders involved.
- High overhead: BDD can introduce a high overhead in terms of development and testing resources. It may require additional resources and personnel to handle the extra complexity and communication involved in the process.