# Data-Driven Teting

DDT is a design pattern that allows you to execute the same test case multiple times with different sets of input data. This pattern separates the test case logic from the test data, making it easy to update and maintain test cases.

```python
import pytest

@pytest.mark.parametrize("a, b, expected_result", [(2, 3, 5), (5, 7, 12), (10, -2, 8)])
def test_addition(a, b, expected_result):
    result = a + b
    assert result == expected_result

@pytest.mark.parametrize("a, b, expected_result", [(5, 2, 3), (7, 5, 2), (10, -2, 12)])
def test_subtraction(a, b, expected_result):
    result = a - b
    assert result == expected_result
```

In this example, we're using the ```@pytest.mark.parametrize``` decorator to specify the test data for each test method. The decorator takes a list of tuples, where each tuple represents a set of input values and their expected output. The test method itself takes the input values as arguments and verifies that the actual result matches the expected result using the ```assert``` statement.

It makes it easy to add or remove test data as needed without having to modify the test method itself. Additionaly, **pytest** provides a lot of features for DDT, such as generating test data dynamically, reading test data from external sources, and more.


## Dynamic Test Data Generation

**pytest** allows you to generate test data dynamically using a variety of built-in functions and libraries, such as ```range()```, ```random()```, and ```datetime()```. For example, set of test data for a date range can be generated using the ```datetime()``` function as follows:

```python
import pytest
from datetime import datetime, timedelta

@pytest.mark.parametrize("date", [datetime.now() + timedelta(days=x) for x in range(5)])
def test_date_range(date):
    assert date.year == 2023
```

In this example, we're generating a set of five dates, starting from the current date and increasing by one day for each test.


## Reading Test Data from External Source

**pytest** allows to read test data from external source such as CSV files, JSON files, and databases.

```python
import pytest
import csv

def get_csv_data():
    with open('test_data.csv') as csv_file:
        reader = csv.reader(csv_file)
        next(reader)  # Skip header row
        for row in reader:
            yield tuple(row)

@pytest.mark.parametrize("a, b, expected_result", get_csv_data())
def test_addition(a, b, expected_result):
    result = int(a) + int(b)
    assert result == int(expected_result)
```

In this example, we're using ```csv``` module to read the test data from a CSV file and yield each row as a tuple of input values and expected result.


## Pros and Cons


**Advantages:**
1. Increased test coverage: with DDT, you can test a large number of test cases with different input data and expected output combinations.
2. Efficient: DDT can significantly reduce the time and effort required to create and execute test cases. Instead of writing separete test cases for each data value, DDT enables you to create a single test script that can handle multiple sets of data.
3. Reusability: with DDT, test scripts can be reused with different sets of test data, making it easier to test various scenarios with minimal effort.
4. Maintenance: if the input data changes, you can update the test data source instead of modifying each test case individually.

**Disadvantages:**
1. Complexity: DDT requires additional setup and scripting compared to other testing techniques, which can make it more complex and time-consuming.
2. Tool dependency: DDT requires tools that can extract data from external sources and incorporate it into the test cases.
3. Difficulty in isolating defects: since DDT involves testing with multiple datasets, it can be difficult to isolate defects and datermine the root cause of failures.
4. Limited flexibility: DDT may not be suitable for all types of testing scenarios. For example, it may not be effective for testing complex interactions between multiple systems.