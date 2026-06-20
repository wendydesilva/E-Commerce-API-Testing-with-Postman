🛒 E-Commerce API Testing with Postman

A comprehensive API testing project built using Postman to validate the functionality and reliability of a RESTful e-commerce API. This project demonstrates API request creation, automated test scripts, collection execution with Newman, and CI/CD integration using GitHub Actions.

📌 Project Overview

This project contains a Postman collection for testing the Fake Store API. It includes automated validations for:

HTTP status codes
Response times
JSON response structures
Data integrity

The project showcases practical API testing skills and continuous integration practices.

🚀 Features
API testing with Postman
Automated assertions using JavaScript
Status code validation
Response time verification
JSON response validation
Collection execution using Newman
HTML report generation
Continuous Integration with GitHub Actions
🛠 Technologies Used
Postman
JavaScript
Newman
GitHub Actions
Fake Store API
📂 Project Structure
E-Commerce-API-Testing-with-Postman/
│
├── collections/
│   └── E-Commerce API.postman_collection.json
│
├── .github/
│   └── workflows/
│       └── api-tests.yml
│
├── report.html
│
└── README.md
🔗 API Under Test

Base URL

https://fakestoreapi.com
Tested Endpoints
Method	Endpoint	Description
GET	/products	Retrieve all products
GET	/products/{id}	Retrieve a specific product
GET	/products/categories	Retrieve all categories
GET	/products/category/{category}	Retrieve products by category
✅ Sample Test Script
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is less than 2000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});

pm.test("Response is an array", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData).to.be.an("array");
});
▶ Running the Collection with Postman
Open Postman.
Import the collection file.
Click Run Collection.
Execute all requests.
Review the test results.
⚙ Running with Newman
Install Newman
npm install -g newman
Execute the Collection
newman run "collections/E-Commerce API.postman_collection.json"
Generate an HTML Report

Install the HTML reporter:

npm install -g newman-reporter-htmlextra

Run:

newman run "collections/E-Commerce API.postman_collection.json" \
-r cli,htmlextra \
--reporter-htmlextra-export report.html
🔄 CI/CD with GitHub Actions

This project uses GitHub Actions to automatically run the Postman collection whenever code is pushed to the repository.

Workflow Steps
Checkout repository
Install Node.js
Install Newman
Run Postman collection
Generate test report
📊 Example Output
E-Commerce API

→ Get All Products
GET https://fakestoreapi.com/products

✓ Status code is 200
✓ Response time is less than 2000ms
✓ Response is an array
🎯 Learning Outcomes

Through this project, I gained experience in:

REST API testing
Writing Postman test scripts
Response validation techniques
Newman command-line execution
Report generation
CI/CD automation with GitHub Actions
👩‍💻 Author

Wendy De Silva

GitHub: https://github.com/wendydesilva

⭐ Support

If you found this project useful, consider giving the repository a star!
