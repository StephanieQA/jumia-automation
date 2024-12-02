# JUMIA Automation Testing Framework

## Overview

This project contains an automation testing framework built using Playwright for testing an e-commerce website (JUMIA). The test script automates the following scenario:

- Navigate to the JUMIA website.
- Search for a specific product.
- Add the product to the cart.
- Proceed to checkout.

The framework includes assertions for each step, handles dynamic elements, and provides robust logging and reporting. It also features a retry mechanism for flaky tests and is integrated with GitHub Actions for CI/CD.


## Features
- Search for Product: Automates searching for a specific product on the e-commerce platform.
- Add to Cart: Adds the product to the cart.
- Checkout Process: Automates the checkout process, including validating the cart contents and ensuring successful checkout.
- Retry Mechanism: Automatically retries flaky tests to improve stability.
- Logging & Reporting: Logs detailed information during test execution, including pass/fail status and error messages.
- CI/CD Integration: The script is integrated with GitHub Actions for continuous integration and deployment.

## Project Structure

- `allure-results`: Contains Allure test results and reports.
- `tests`:Test scripts folder.
- `ecommerce.spec.js`: Playwright test script for e-commerce checkout.
- `utils`: Utility scripts for supporting tasks (e.g., email OTP fetching).
- `utils`: Playwright configuration file.
- `README.md `: This documentation.

## Prerequisites

Before running the tests, ensure you have the following installed:

- **Node.js** (version 16.x or later)
- **Playwright** (for web automation)
- **Allure** (for test reporting)

To install dependencies, run:

```bash
npm install

## Setup

### Clone the Repository

```bash
  git clone [https://your-repository-url.git](https://github.com/StephanieQA/jumia-automation.git)
  cd [your-repository-folder](https://github.com/StephanieQA/jumia-automation.git)
```

### Install Dependencies

Ensure you have the required npm packages:

```bash
npm install
```

Install Playwright browsers:

```bash
npx playwright install
```

### Configure Environment Variables

Create a `.env` file in the root directory and add the following variables:

```env
PHONENUMBER=your_phone_number
PASSWORD=your_password

OTP_EMAIL=your_email_address
OTP_EMAIL_PASSWORD=your_email_password

CARD_NUMBER=
CARD_EXP_MONTH=
CARD_EXP_YEAR=
CARD_CVC=
```

### Prepare Test Data

Ensure `testData.json` is present in the root directory with the required structure:

```json
{
  "searchTerms": ["iphone 15", "samsung galaxy s21", "oneplus 9"]
}
```

## Running the Tests

To run the Playwright tests, execute the following command:

```bash
npx playwright test
```

To run tests with the Playwright UI, use:

```bash
npx playwright test --ui
```

## Logging

The test logs are saved in `test-log.txt` in the root directory. Logs include navigation steps, actions performed, and any errors encountered.

## Test Details

### Checkout and Payment Process

#### Checkout Process
1. Navigate to the homepage.
2. Search for a product using the first search term from `testData.json`.
3. Add the first search result to the cart.
4. Proceed to the cart and click on the Checkout button.

#### Payment Process
1. Log in with the provided phone number and password.
2. Enter the OTP digits.
3. Confirm the order and navigate through payment options.
4. Enter payment details and complete the payment process.

## Troubleshooting

- **Browser Not Found**: If you encounter an error about missing browser executables, ensure you have run `npx playwright install` to download the required browsers.
- **Environment Variables**: Verify that all required environment variables are correctly set in your `.env` file.
- **File Paths**: Check that `testData.json` and other required files are present in the correct locations.
- **Fetching OTP: Ensure the email service script (utils/emailService.js) is correctly implemented and that your email credentials are set up properly.
