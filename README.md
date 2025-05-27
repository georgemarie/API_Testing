# 🧪 FakeStoreAPI Postman Test Suite

This Postman collection tests key endpoints from the [FakeStore API](https://fakestoreapi.com/), covering user management, product listings, and cart operations.

---

## 📦 Setup Instructions

### 1. Import Collection
- Open Postman.
- Click **Import** → **Upload Files**.
- Select: `FakeStoreAPI.postman_collection.json`.

### 2. (Optional) Import Environment
- Import `FakeStoreAPIEnvironment.postman_environment.json` if using variables.

---

## 🚀 Test Scenarios

| #  | Name                               | Method   | Endpoint              | Status Test | Notes                          |
|----|------------------------------------|----------|-----------------------|-------------|--------------------------------|
| 1  | ✅ Create Valid User               | POST     | `/users`              | 200         | Returns user ID                |
| 2  | ❌ Create User - Missing Username  | POST     | `/users`              | 400         | Missing required field         |
| 3  | ❌ Create User - Missing Password  | POST     | `/users`              | 400         | Missing required field         |
| 4  | ❌ Create User - No Fields         | POST     | `/users`              | 400         | No data provided               |
| 5  | ✅ Get All Users                   | GET      | `/users`              | 200         | Non-empty array                |
| 6  | ✅ Get Users in City               | GET      | `/users?city={city}`  | 200         | Filter by city parameter       |
| 7  | ✅ Login User                      | POST     | `/auth/login`         | 200         | Includes token                 |
| 8  | ❌ Invalid Login                   | POST     | `/auth/login`         | 401         | Wrong credentials              |
| 9  | ✅ Get All Products                | GET      | `/products`           | 200         | Non-empty array                |
| 10 | ❌ Invalid Get Products            | GET      | `/invalid-products`   | 404         | Invalid endpoint               |
| 11 | ✅ Get Product by ID               | GET      | `/products/1`         | 200         | Contains `title`               |
| 12 | ❌ Invalid Get Product by ID       | GET      | `/products/invalid`   | 404         | Non-existent product ID        |
| 13 | ✅ Create Cart                     | POST     | `/carts`              | 201         | Returns cart ID                |
| 14 | ❌ Create Invalid Cart             | POST     | `/carts`              | 400         | Missing required fields        |
| 15 | ✅ Get Single Cart by ID           | GET      | `/carts/1`            | 200         | Contains user & products       |
| 16 | ❌ Invalid Get Cart by ID          | GET      | `/carts/invalid`      | 404         | Non-existent cart ID           |
| 17 | ✅ Delete Cart                     | DELETE   | `/carts/1`            | 200         |                                |
| 18 | ❌ Invalid Cart Deletion           | DELETE   | `/carts/invalid`      | 404         | Non-existent cart ID           |
| 19 | ✅ Get All Carts                   | GET      | `/carts`              | 200         | Non-empty array                |
| 20 | ✅ Get Carts for a User            | GET      | `/carts?userId=1`     | 200         | Filter by user ID              |

---

## ❗ Notes
- Replace `{city}` and `userId=1` with actual values during testing.
- Some features (e.g., city filters) are **hypothetical** and included for demonstration purposes.
- The FakeStore API may not support all listed filters natively.

---

## 📁 Files Included
- `FakeStoreAPI.postman_collection.json`
- `README.md`
