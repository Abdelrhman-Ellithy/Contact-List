# Contact List API Testing Project 🚀

This project contains a set of API tests for the [Contact List API](https://thinking-tester-contact-list.herokuapp.com/), an API for managing contacts. The tests are automated using Postman 🛠️ and executed via Newman, ensuring coverage of key API functionalities such as login, contact creation, retrieval, updating, and deletion.

![Postman Logo](https://upload.wikimedia.org/wikipedia/commons/c/c2/Postman_%28software%29.png)

## Table of Contents

- [Project Overview](#project-overview)
- [API Endpoints Tested](#api-endpoints-tested)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Tests](#running-the-tests)
- [Environment Setup](#environment-setup)
- [Test Collection Structure](#test-collection-structure)
- [Contributing](#contributing)
- [License](#license)

## Project Overview

The purpose of this project is to automate testing of the Contact List API to ensure the functionality of various endpoints such as login, contact creation, retrieval, updating, and deletion. These tests are written in Postman 🛠️ and executed via Newman, providing robust API validation with environment variables to support dynamic testing.

### Technologies Used:
- **Postman** for API request creation and test scripting. 🛠️
- **Newman** for command-line execution of Postman collections.
- **Node.js** for running Newman and managing dependencies. 🖥️

![NPM Logo](https://th.bing.com/th/id/OIP.W9KqKY8XIN2U66v1oa7TYgHaGa?w=179&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7)

## API Endpoints Tested

The following API endpoints are covered in this test suite:

1. **Login** (`POST /users/login`)
2. **Add Contact** (`POST /contacts`)
3. **Get Contact List** (`GET /contacts`)
4. **Get Single Contact** (`GET /contacts/{id}`)
5. **Edit Contact** (`PUT /contacts/{id}`)
6. **Delete Contact** (`DELETE /contacts/{id}`)

## Prerequisites 🔧

Before running the tests, ensure that you have the following installed:

- [Node.js](https://nodejs.org/en/download/) (v10 or higher) 🖥️
- [npm](https://www.npmjs.com/get-npm) (bundled with Node.js) 📦
- [Postman](https://www.postman.com/downloads/) (for test development) 🛠️
- [Newman](https://www.npmjs.com/package/newman) (for running Postman collections via CLI)

## Installation 📦

Install Newman globally via npm:

```bash
npm install -g newman
```

## Running the Tests 🏃‍♂️

To execute the test suite, use Newman with the provided collection and environment files:

```bash
newman run 'ContactList-WebSite.collection.json' -e 'ContactList-Env.json'
```

- **`ContactList-WebSite.collection.json`**: Postman collection containing API tests.
- **`ContactList-Env.json`**: Postman environment file containing dynamic variables.

This will run all tests included in the collection and display the results in the terminal. 🎯

## Environment Setup 🌐

The Postman environment file (`ContactList-Env.json`) includes dynamic variables such as:

- `baseURL`: Base URL of the API (`https://thinking-tester-contact-list.herokuapp.com`)
- `token`: Authentication token for protected endpoints.
- `firstname`: First name for the contact.
- `lastname`: Last name for the contact.
- `Contact-ID`: ID of the last created contact.

### Steps to Set Up the Environment:

1. Open Postman and go to **Environments**.
2. Create a new environment and define the following variables:
   - `baseURL`
   - `token`
   - `firstname`
   - `lastname`
3. Export this environment file as `ContactList-Env.json`.

## Test Collection Structure 📑

The Postman collection contains the following requests and test scripts:

### 1. **Login** (`POST /users/login`)
- **Test Script**:
  - Verifies the status code is 200.
  - Validates response time is less than 1000ms.
  - Checks that the `token` is returned and saved in the environment.

### 2. **Add Contact** (`POST /contacts`)
- **Test Script**:
  - Ensures the status code is 201.
  - Checks response time is less than 1000ms.
  - Validates the contact details (first and last names).

### 3. **Get Contact List** (`GET /contacts`)
- **Test Script**:
  - Verifies the status code is 200.
  - Checks response time is less than 1000ms.
  - Confirms the first contact's details are correct.

### 4. **Get Single Contact** (`GET /contacts/{id}`)
- **Test Script**:
  - Validates the status code is 200.
  - Checks response time and contact details.

### 5. **Edit Contact** (`PUT /contacts/{id}`)
- **Test Script**:
  - Verifies the status code is 200.
  - Ensures the updated contact details are correct.

### 6. **Delete Contact** (`DELETE /contacts/{id}`)
- **Test Script**:
  - Confirms the status code is 200.
  - Checks response time is less than 500ms.

## Contributing 🤝

Contributions are welcome! Please fork the repository and submit a pull request.

## License 📜

This project is licensed under the MIT License. See the `LICENSE` file for details.