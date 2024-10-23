# Application 1: Rule Engine using AST

![Preview](image) <!-- Replace with actual image link -->
![Screenshot 2024-10-22 144803](https://github.com/user-attachments/assets/516c072d-3ff3-494f-a3bd-f3df9ff1b80f)
![Screenshot 2024-10-22 144434](https://github.com/user-attachments/assets/5b7087d6-3f09-4624-b594-8969366e4dcf)
![Screenshot 2024-10-22 144206](https://github.com/user-attachments/assets/18a1a2ad-efa3-4c12-b230-b150c91fcb34)
![Screenshot 2024-10-22 144055](https://github.com/user-attachments/assets/3b0478d8-b570-4ee1-a302-9f2c9f51e6fc)

## Overview
This application functions as a rule engine that assesses user eligibility based on various attributes, including age, department, salary, and experience. It employs an Abstract Syntax Tree (AST) for representing and managing conditional rules, facilitating the dynamic creation, combination, and evaluation of rules.

## Features
- *Rule Creation*: Users can define rules using a string format, which is then transformed into an AST.
  
  ![Rule Creation](image) <!-- Replace with actual image link -->

- *Rule Combination*: Allows the merging of multiple rules into a singular AST to enable more intricate evaluations.

  ![Rule Combination](image) <!-- Replace with actual image link -->

- *Rule Evaluation*: Assesses whether the provided data aligns with the criteria set by the AST.

  ![Rule Evaluation](image) <!-- Replace with actual image link -->

- *Tree Visualization*: When defining or combining rules, a tree representation will be displayed for better understanding.

## Tech Stack
- *Backend*: Node.js, Express.js
- *Database*: MongoDB

## Getting Started

### Prerequisites
Ensure you have Node.js and npm installed on your machine.

### Installation Steps
1. Clone the Repository:
   bash
   git clone "https://github.com/amangupta3317/Rule-Engine-with-AST-main/edit/master.git"
   

2. Navigate to the project directory:
   bash


   cd Rule-Engine-with-AST-main/edit/master
   

4. Install the Backend Dependencies:
   bash
   npm install
   

5. Create a .env file in the root directory and add your MongoDB URL:
   env
   MONGO_URL=""
   

6. Launch the Server:
   bash
   npm start
   

## API Endpoints

### Create a Rule
- *Endpoint*: /api/create_rule
- *Method*: POST
- *Request Body*:
  json
  {
    "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)",
    "ruleName": "Rule-1"
  }
  
  *Note*: Ensure that there are appropriate spaces in the rule for accurate results. The rule should follow this format: variable operator value.

- *Response*: 
  json
  {
    "message": "Rule created successfully",
    "ruleId": "abc123"
  }
  
  ![Response Image](image) <!-- Replace with actual image link -->

### Combine Rules
- *Endpoint*: /api/rules/combine_rules
- *Method*: POST
- *Request Body*:
  json
  {
    "rules": [
      { "ruleId": "ruleId1" },
      { "ruleId": "ruleId2" }
    ]
  }
  

- *Response*:
  json
  {
    "message": "Rules combined successfully",
    "combinedRuleId": "xyz789"
  }
  
  ![Response Image](image) <!-- Replace with actual image link -->

### Evaluate a Rule
- *Endpoint*: /api/rules/evaluate_rule
- *Method*: POST
- *Request Body*:
  json
  {
    "rule": { "ruleId": "abc123" },
    "data": {
      "age": 35,
      "department": "Sales",
      "salary": 60000,
      "experience": 3
    }
  }
  

- *Response*:
  json
  {
    "result": true
  }
  

## Running Tests
You can implement and execute tests to verify that everything is functioning as expected.

## License
This project is licensed under the MIT License.
