# QA API Testing with Postman

This repository contains API testing simulations using [Reqres](https://reqres.in/) API, tested with Postman.

## 🔧 Tools Used
- Postman
- Reqres.in (Fake API for Testing)
- GitHub

## Extended Header for `reqres.in`
- x-api-key: reqres-free-v1

## ✅ Test Cases

### 1. Login (Get Token)
- **Method:** `POST`
- **Endpoint:** `https://reqres.in/api/login`
- **Input:** Email & Password
- **Expected Result:** Status `200 OK` and receive token

---

### 2. Get User Detail with Valid Token
> *Note: Although Reqres.in doesn't enforce token validation, this simulates a positive test case using a token.*
- **Method:** `GET`
- **Endpoint:** `https://reqres.in/api/users/2`
- **Header:** `Authorization: Bearer validtoken123` *(simulated)*
- **Expected:** Status `200 OK` and user data returned
- **Actual:** Status `200 OK`

---

### 3. Get User Detail with Wrong Token (Negative Test)
> *Note: This is to simulate behavior when token is invalid.*
- **Method:** `GET`
- **Endpoint:** `https://reqres.in/api/users/2`
- **Header:** `Authorization: Bearer wrongtoken123`
- **Expected:** Status `401 Unauthorized`
- **Actual:** Status `200 OK` (because Reqres.in doesn't validate tokens)

## 📸 Screenshots
You can find request and response examples in the `Screenshots/` folder.

---

## 📁 How to Run
1. Open Postman
2. Import the collection from `Collection/API Auth Testing.postman_collection.json`
3. Run the requests manually or using Postman Runner
