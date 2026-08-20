# Selenium Python Pytest Automation

A UI test automation framework built using **Python, Selenium WebDriver, and Pytest** following the **Page Object Model (POM)** design pattern.

The framework demonstrates reusable page objects, data-driven testing, explicit waits, automated screenshots on test failure, and HTML test reporting.

## Tech Stack

* **Python** — Programming language
* **Selenium WebDriver** — Web UI automation
* **Pytest** — Test framework
* **Page Object Model (POM)** — Framework design pattern
* **JSON** — Test data management
* **pytest-html** — Test reporting
* **Git & GitHub** — Version control

## Application Under Test

The framework uses the public **Sauce Demo** application for UI automation practice.

Application URL:

https://www.saucedemo.com/

## Project Structure

```text
selenium-python-pytest-automation/
│
├── pages/
│   └── login_page.py
│
├── tests/
│   └── test_login.py
│
├── utils/
│   └── data_reader.py
│
├── test_data/
│   └── login_data.json
│
├── screenshots/
├── reports/
│
├── conftest.py
├── pytest.ini
├── requirements.txt
├── .gitignore
└── README.md
```

## Automated Test Scenarios

The login functionality currently covers:

| Test Scenario                 | Expected Result                          |
| ----------------------------- | ---------------------------------------- |
| Valid username and password   | User successfully logs in                |
| Invalid username and password | Appropriate error message is displayed   |
| Empty username                | Username validation message is displayed |
| Empty password                | Password validation message is displayed |

## Framework Features

### Page Object Model

Web elements and page actions are maintained separately from the test cases.

Example:

```python
login_page.enter_username(username)
login_page.enter_password(password)
login_page.click_login()
```

This improves code readability, maintainability, and reusability.

### Data-Driven Testing

Login test data is maintained separately in:

```text
test_data/login_data.json
```

Pytest parametrization is used to execute the same test with multiple data sets.

### Explicit Waits

The framework uses Selenium `WebDriverWait` and expected conditions instead of relying on fixed waits wherever possible.

Example:

```python
WebDriverWait(driver, 10)
```

This helps make the tests more reliable when page elements take different amounts of time to load.

### Automatic Screenshots on Failure

When a test fails, the framework automatically captures a screenshot and stores it locally under:

```text
screenshots/
```

Generated screenshots are excluded from Git tracking using `.gitignore`.

### HTML Test Reporting

HTML reports can be generated using `pytest-html`.

```bash
pytest --html=reports/test_report.html --self-contained-html
```

The generated report contains test execution details including test status and execution information.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/DiosaNandhini/selenium-python-pytest-automation.git
```

### 2. Navigate to the project

```bash
cd selenium-python-pytest-automation
```

### 3. Create and activate a virtual environment

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

## Running the Tests

Run all tests:

```bash
pytest -v
```

Run the login tests:

```bash
pytest tests/test_login.py -v
```

Generate an HTML report:

```bash
pytest --html=reports/test_report.html --self-contained-html
```

## Test Execution

Current test coverage:

**4 login scenarios**

* Valid login
* Invalid credentials
* Empty username
* Empty password

All current automated tests are passing.

## Future Enhancements

Planned improvements to the framework include:

* Add more UI test scenarios
* Add additional Page Object classes
* Improve test reporting
* Add CI/CD using GitHub Actions
* Add Playwright automation
* Add cross-browser execution
* Integrate API testing
* Improve test configuration management

## Author

**DiosaNandhini**

QA Engineer | Manual & Automation Testing

Skills demonstrated in this project include Selenium, Python, Pytest, Page Object Model, test data management, and automated reporting.
