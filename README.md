# ServeRest API Tests

API test automation project developed with Postman and Newman using the ServeRest API.

This project covers positive and negative test scenarios for authentication, users, products, and cart functionalities, simulating real e-commerce API flows.

---

# Technologies

- Postman
- Newman
- JavaScript
- Node.js
- ServeRest API

---

# Project Structure

```txt
serverest-api-tests
│
├── collection
│   └── ServeRest_API_Tests.json
│
├── environment
│   └── ServeRest_Environment.json
│
├── reports
│   └── report.html
│
├── docs
│   └── index.html
│
├── images
│
├── README.md
│
└── .gitignore
```

---

# Test Coverage

## Authentication
- Login Success
- Login Invalid Password
- Login Without Email

---

## Users
- Create User Success
- Validate Created User
- Delete Existing User
- Validate Deleted User
- Delete Nonexistent User
- Get Nonexistent User
- Create User Without Email

---

## Products
- Create Product Success
- Validate Created Product
- Delete Product
- Validate Deleted Product
- Get All Products
- Create Product Without Token
- Create Product Without Name

---

## Cart
- Add Product To Cart
- Validate Cart
- Checkout Cart
- Add Invalid Product To Cart
- Checkout Empty Cart

---

# Automated Flow

The project includes an end-to-end automated flow using request chaining and environment variables.

```txt
Create User
↓
Validate User
↓
Login
↓
Create Product
↓
Validate Product
↓
Add Product To Cart
↓
Validate Cart
↓
Checkout Cart
↓
Delete Product
↓
Validate Deleted Product
↓
Delete User
↓
Validate Deleted User
```

---

# Setup Folder

The collection also contains a reusable Setup folder responsible for preparing test data before executing independent scenarios.

Setup includes:

- Create Test User
- Login Test User
- Create Test Product

This approach reduces test dependency and improves suite organization.

---

# Validations Implemented

- Status code validation
- Response body validation
- Response time validation
- Authentication validation
- Required fields validation
- Duplicate data validation
- Resource existence validation

---

# Running the Tests

## Requirements

- Node.js installed
- Newman installed

---

# Install Newman

```bash
npm install -g newman
```

---

# Install HTML Reporter

```bash
npm install -g newman-reporter-htmlextra
```

---

# Run Complete Collection

```bash
newman run collection/ServeRest_API_Tests.postman_collection.json -e environment/ServeRest_ENV.postman_environment.json

```

---

# Run Specific Folders

## Setup + Products

```bash
newman run collection/ServeRest_API_Tests.json -e environment/ServeRest_Environment.json --folder "Setup" --folder "Products"
```

---

## Setup + Cart

```bash
newman run collection/ServeRest_API_Tests.json -e environment/ServeRest_Environment.json --folder "Setup" --folder "Cart"
```

---

## Happy Path Flow

```bash
newman run collection/ServeRest_API_Tests.json -e environment/ServeRest_Environment.json --folder "Happy Path Flow"
```

---

# Generate HTML Report

```bash
newman run collection/ServeRest_API_Tests.json -e environment/ServeRest_Environment.json -r htmlextra --reporter-htmlextra-export reports/report.html
```

---

# HTML Test Report

The project includes an online HTML execution report published with GitHub Pages.

[View Online Report](https://lizandra-p.github.io/serverest-api-tests/)

---

# API Used

ServeRest API:

https://serverest.dev/

---

# Author

Lizandra Pontes
email: lizandraptes@gmail.com
