# 🧪 FakeStoreAPI Postman Test Suite

This Postman collection tests key endpoints from the [FakeStore API](https://fakestoreapi.com/), including functionality such as user creation, login, product management, and cart operations.

---

## 📦 Setup Instructions

### 1. Import Collection
- Open Postman.
- Click **Import** → **Upload Files**.
- Select: `FakeStoreAPI.postman_collection.json`.

### 2. (Optional) Import Environment
- If using an environment file, import `FakeStoreAPIEnvironment.postman_environment.json`.

---

## 🚀 Test Scenarios Included

| #  | Name                    | Method   | Endpoint         | Status Test | Notes                      |
|----|-------------------------|----------|------------------|-------------|----------------------------|
| 1  | ✅ Create User           | POST     | `/users`         | 200         | Returns user ID            |
| 2  | ✅ Get All Users         | GET      | `/users`         | 200         | Non-empty array            |
| 3  | ✅ Login User            | POST     | `/auth/login`    | 200         | Includes token             |
| 4  | ✅ Get All Products      | GET      | `/products`      | 200         | Non-empty array            |
| 5  | ✅ Get Product by ID     | GET      | `/products/1`    | 200         | Contains `title`           |
| 6  | ✅ Create Cart           | POST     | `/carts`         | 201         | Returns cart ID            |
| 7  | ✅ Get Cart by ID        | GET      | `/carts/1`       | 200         | Contains user & products   |
| 8  | ✅ Delete Cart           | DELETE   | `/carts/1`       | 200         |                            |
| 9  | ✅ Get All Carts         | GET      | `/carts`         | 200         | Non-empty array            |
| 10 | ❌ Negative Tests        | All      | Various          | 4xx/5xx     | Invalid input tests        |

---

## ❗ Negative Test Coverage

Each scenario includes a negative test such as:

- Invalid user data
- Wrong login credentials
- Invalid product/cart ID
- Missing fields

Check the collection folder named **"❌ Negative Tests"** for full list.

---

## 🔧 Dependencies

- Postman v10 or higher
- Internet connection (uses a public API)

---

## 📁 Files Included

- `FakeStoreAPI.postman_collection.json`
- `FakeStoreAPIEnvironment.postman_environment.json` (Optional)
- `README.md` (this file)

