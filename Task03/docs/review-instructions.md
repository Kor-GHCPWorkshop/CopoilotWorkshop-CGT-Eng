<!-- Copilot Code Review Instructions -->

# Code Review Guidelines

This document provides the guidelines to follow when performing code reviews for the project.

## 1. Code Style
- Follow the [Python Style Guide](./python-style.md) for Python code.
- Check that function, variable, and class names follow naming conventions.
- Check code readability, including indentation, whitespace, and comments.

## 2. Functionality Verification
- Ensure the written code meets the requirements.
- Test that all major features work correctly.
- Check that exception handling and error handling are properly implemented.

## 3. Security
- Verify that user input is validated.
- Ensure sensitive data (e.g., passwords) is handled securely.
- Check that database queries are not vulnerable to SQL Injection.

## 4. Performance
- Check for unnecessary complexity or inefficiency in the code.
- Review loops and database queries for optimization.

## 5. Testing
- Ensure sufficient test code has been written.
- Check that tests cover all major features.
- Confirm that tests pass successfully.

## 6. Documentation
- Check that appropriate docstrings are written for functions, classes, and modules.
- Ensure comments clearly explain the intent of the code.
- Verify that README.md and related documentation are up to date.

## 7. Other
- Check for unnecessary code, comments, or debugging output.
- Ensure the code is modular and written for reusability.