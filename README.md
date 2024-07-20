# Adjutor API Test Scripts [N.B Switch to master branch]

This repository contains Postman test scripts for testing Adjutor APIs.

## Setup and Run

To set up and run the test scripts, follow these steps:

1. **Install Postman**: Ensure you have Postman installed on your machine. You can download it from [here](https://www.postman.com/downloads/).

2. **Import Collection**: Open Postman, click on `Import` and select the `AdjutorAPI.postman_collection.json` file from this repository.

3. **Set Up Collection Variables**:
   - After importing the collection, navigate to the `Collections` tab.
   - Select the `Adjutor API Servive [Lendsqr test]` collection.
   - Click on `Variables` to view the collection variables.
   - Set the following variables with the appropriate values:
     - `{{base_url}}`: https://adjutor.lendsqr.com/v2/
     - `{{access_token}}`: sk_live_68NIHVllnbB1jcV3h4hXiChAu8PKZ2478FyO4HV3


4. **Run Collection**: 
    - Click on the `Collection Runner` in Postman 
    - select the imported collection
    - Navigate to the advanced setting and Click
    - Uncheck the "stop run if an error occurs"
    - Click `Run Adjutor API Servive [Lendsqr test]`.

## Test Results

Summary of test results:

- **Validation [Check Karma for Customers]**
  - Success Request: Passed
  - No Karma Identity: Incomplete
  - Invalid Auth: Passed

- **Validation [Check for Borrower on Ecosystem]**
  - Success Request: Failed (504 Gateway Timeout)
  - Invalid BVN: Failed (504 Gateway Timeout)
  - Invalid Auth: Passed

- **Credit Bureaus [Get Credit Report from CRC Credit Bureau]**
  - Success Request: Failed (500 Internal Server Error)
  - No CRC History: Failed (500 Internal Server Error)
  - Invalid BVN: Failed (500 Internal Server Error)
  - Invalid Auth: Passed

- **Credit Bureaus [Get Credit Report from FirstCentral Credit Bureau]**
  - Success Request: Passed
  - Invalid BVN: Failed (200 was returned instead of 400)
  - Invalid Auth: Passed

- **Decisioning [Get Decision Models]**
  - Success Request: Passed
  - Invalid Auth: Passed

- **Decisioning [Get Decision Model Details]**
  - Success Request: Passed
  - Invalid ID: Failed (500 was returned instead of 404)
  - Invalid Auth: Passed

- **Embedded Loans and Payment [Loans: Initialize Loan Application]**
  - Success Request: Blocked (Product id is "null")
  - Empty Mandatory Field: Failed (504 Gateway Timeout)
  - Invalid Product ID: Incomplete (Error message should be updated)
  - Invalid Email: Incomplete (Error message should be updated)
  - Invalid Phone Number: Incomplete (Error message should be updated)
  - Invalid Auth: Passed

- **Embedded Loans and Payment [Loans: Get Loan Products]**
  - Success Request: Failed (400 was returned)
  - Invalid Auth: Passed

- **Data for Lenders [Options]**
  - Success Request: Incomplete (Response doesn't contain message)
  - Invalid Auth: Passed

- **Data for Lenders [Users]**
  - Success Request: Incomplete (Response doesn't contain message)
  - Invalid Auth: Passed

- **Operational Service [Profile: Get Wallet]**
  - Success Request: Passed
  - Invalid Auth: Passed

- **Operational Service [Profile: Get Adjutor Services Pricing]**
  - Success Request: Passed
  - Invalid Auth: Passed

- **Direct Debit [Banks: Get All Banks]**
  - Success Request: Passed
  - Invalid Auth: Passed

- **Direct Debit [Banks: Get Details of Bank]**
  - Success Request: Passed
  - Invalid Bank ID: Failed (200 was returned instead of 404)
  - Invalid Auth: Passed
