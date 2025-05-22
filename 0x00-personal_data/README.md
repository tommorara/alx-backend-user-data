# 0x00. Personal data

## 📚 Project Overview

This project focuses on handling **Personally Identifiable Information (PII)** securely in a backend context. You’ll learn how to properly log sensitive user data, hash passwords, and connect to a MySQL database using environment variables—best practices every backend engineer should know to ensure user privacy and system security.

---

## 🎯 Learning Objectives

By completing this project, you should be able to:

- Identify and define types of PII
- Obfuscate sensitive data in logs using regex
- Implement custom logging formatters
- Authenticate to a database securely using environment variables
- Hash and validate passwords using the `bcrypt` library

---

## ⚙️ Requirements

- All code written in Python 3.7
- Must be executable with `#!/usr/bin/env python3` as the first line
- Follows `pycodestyle` (v2.5) standards
- Proper module, class, and method/function docstrings required
- All functions should be type-annotated
- A `README.md` file is mandatory

---

## 🧠 Tasks Summary

### `filtered_logger.py`

#### ✅ 0. Regex-ing
- Implement `filter_datum(fields, redaction, message, separator)`
- Obfuscates specified fields using regex substitution.

#### ✅ 1. Log formatter
- Define `RedactingFormatter(logging.Formatter)` class
- Accepts a list of PII fields and uses `filter_datum` to redact log output.

#### ✅ 2. Create logger
- Implement `get_logger()` to return a properly formatted logger
- Define `PII_FIELDS` tuple with sensitive fields like `name`, `email`, `ssn`, etc.

#### ✅ 3. Connect to secure database
- Implement `get_db()` to connect to a MySQL database using environment variables:
  - `PERSONAL_DATA_DB_USERNAME` (default: `root`)
  - `PERSONAL_DATA_DB_PASSWORD` (default: `""`)
  - `PERSONAL_DATA_DB_HOST` (default: `localhost`)
  - `PERSONAL_DATA_DB_NAME`

#### ✅ 4. Read and filter data
- Implement a `main()` function that:
  - Connects to the DB
  - Logs user data while redacting PII fields using the configured logger

---

### `encrypt_password.py`

#### ✅ 5. Encrypting passwords
- `hash_password(password: str) -> bytes`
- Hashes and salts a password using `bcrypt`

#### ✅ 6. Check valid password
- `is_valid(hashed_password: bytes, password: str) -> bool`
- Compares a plain password against its hashed version

---

## 🛠️ Technologies Used

- Python 3.7
- `bcrypt` for password hashing
- `mysql-connector-python` for MySQL integration
- `logging` for logging functionality
- `re` for regex field obfuscation

---

## 🗂️ Directory Structure


