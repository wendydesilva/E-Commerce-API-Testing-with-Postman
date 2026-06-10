# 📊 Postman API Test Report - E-Commerce API

## 📌 Project Information

| Item | Details |
|--------|---------|
| **API** | FakeStore API |
| **Base URL** | https://fakestoreapi.com |
| **Testing Tool** | Postman |
| **Test Type** | API Functional Testing |


---

## 📈 Test Execution Summary

| Total Test Cases | Passed | Failed |
|-----------------|---------|---------|
| 3 | ✅ 3 | ❌ 0 |

---

# 🧪 Test Case Details

---

## TC-01: Get All Products

### Endpoint

```http
GET /products?limit=5
```

### Expected Result

- Status code should be **200**
- Response time should be **less than 2000 ms**
- Response should contain product information

### Actual Result

- Status code = **200**
- Response time = **519 ms**
- Product data returned successfully

### Status

✅ **PASS**

---

## TC-02: Get Single Product

### Endpoint

```http
GET /products/1
```

### Expected Result

- Status code should be **200**
- Response body should contain:
  - `id`
  - `title`
  - `price`

### Actual Result

- Status code = **200**
- `id` found
- `title` found
- `price` found

### Status

✅ **PASS**

---

## TC-03: Delete Product

### Endpoint

```http
DELETE /products/1
```

### Expected Result

- Status code should be **200**
- Deleted product information should be returned

### Actual Result

- Status code = **200**
- Product deletion response received successfully

### Status

✅ **PASS**

---

# 💻 Test Scripts Used
### Get All Products
```javascript
// Validate status code
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Validate response time
pm.test("Response time is less than 2000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});

// Validate response body fields
pm.test("Response has required fields", function () {
    const jsonData = pm.response.json();

    pm.expect(jsonData).to.have.property("id");
    pm.expect(jsonData).to.have.property("title");
    pm.expect(jsonData).to.have.property("price");
});
```
### Get Single Product
```javascript
// Validate status code
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Validate response time
pm.test("Response time is less than 2000ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(2000);
});

// Parse JSON response
const jsonData = pm.response.json();

// Validate required fields
pm.test("Response contains id", function () {
    pm.expect(jsonData).to.have.property("id");
});

pm.test("Response contains title", function () {
    pm.expect(jsonData).to.have.property("title");
});

pm.test("Response contains price", function () {
    pm.expect(jsonData).to.have.property("price");
});

pm.test("Response contains category", function () {
    pm.expect(jsonData).to.have.property("category");
});

pm.test("Response contains description", function () {
    pm.expect(jsonData).to.have.property("description");
});

// Validate data types
pm.test("Product id is a number", function () {
    pm.expect(jsonData.id).to.be.a("number");
});

pm.test("Product title is a string", function () {
    pm.expect(jsonData.title).to.be.a("string");
});

pm.test("Product price is a number", function () {
    pm.expect(jsonData.price).to.be.a("number");
});

// Validate product ID
pm.test("Product ID equals 1", function () {
    pm.expect(jsonData.id).to.eql(1);
});

// Validate price is positive
pm.test("Price is greater than zero", function () {
    pm.expect(jsonData.price).to.be.above(0);
});
```

---

# 📋 Conclusion

All test cases executed successfully.

### Key Observations

- ✅ API endpoints behaved as expected.
- ✅ Response times were within acceptable limits.
- ✅ Response bodies contained the required fields.
- ✅ No failures were encountered during execution.

---

# 🎯 Overall Result

# ✅ PASS
