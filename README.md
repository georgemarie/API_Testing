# 🧪 FakeStoreAPI Postman Test Suite

Comprehensive API testing for [FakeStoreAPI](https://fakestoreapi.com) with 20 individual test cases.

---

## 📦 Setup
1. **Import Collection**  
   `API Testing.postman_collection.json`
2. **Base URL**: Pre-configured to `https://fakestoreapi.com`

---

## 🚀 Complete Test List

| #  | Test Case Name                     | Method | Endpoint                     | Status | Validation Criteria                          |
|----|------------------------------------|--------|------------------------------|--------|----------------------------------------------|
| 1  | Create Valid User                  | POST   | `/users`                     | 200    | Returns user ID                              |
| 2  | Create User - Missing Username     | POST   | `/users`                     | 400    | Validates username requirement               |
| 3  | Create User - Missing Password     | POST   | `/users`                     | 400    | Validates password requirement               |
| 4  | Create User - No Fields            | POST   | `/users`                     | 400    | Rejects empty payload                        |
| 5  | Get All Users                      | GET    | `/users`                     | 200    | Returns non-empty array                      |
| 6  | Get Users in San Antonio           | GET    | `/users?city=San Antonio`    | 200    | All users have San Antonio city              |
| 7  | Login User                         | POST   | `/auth/login`                | 200    | Returns JWT token                            |
| 8  | Invalid Login                      | POST   | `/auth/login`                | 401    | Error message for wrong credentials          |
| 9  | Get All Products                   | GET    | `/products`                  | 200    | Returns product array                        |
| 10 | Filter Men's Clothing              | GET    | `/products?category=men's...`| 200    | All in men's clothing category               |
| 11 | Get Product by ID (Valid)          | GET    | `/products/1`                | 200    | Contains title field                         |
| 12 | Get Product by ID (Invalid)        | GET    | `/products/-1`               | 400    | Handles negative IDs                         |
| 13 | Create Valid Cart                  | POST   | `/carts`                     | 201    | Returns cart ID with products                |
| 14 | Create Invalid Cart                | POST   | `/carts`                     | 400    | Rejects non-integer quantities               |
| 15 | Get Single Cart (Valid)            | GET    | `/carts/1`                   | 200    | Validates product structure                  |
| 16 | Get Single Cart (Invalid)          | GET    | `/carts/aa`                  | 400    | Handles non-numeric IDs                      |
| 17 | Delete Cart (Valid)                | DELETE | `/carts/1`                   | 200    | Successful deletion                          |
| 18 | Delete Cart (Invalid)              | DELETE | `/carts/-1`                  | 404    | Handles non-existent carts                   |
| 19 | Get All Carts                      | GET    | `/carts`                     | 200    | Returns cart array                           |
| 20 | Get Carts for User ID 5            | GET    | `/carts?userId=5`            | 200    | All carts belong to user 5                   |

---

## 🔍 Test Details
### User Tests (#1-6)
- Full user lifecycle testing with field validation
- City filtering demonstrates parameter handling

### Auth Tests (#7-8)
- Complete authentication flow coverage
- Error message verification for security

### Product Tests (#9-12)
- Basic CRUD operations
- Category filtering implementation
- Boundary testing with negative IDs

### Cart Tests (#13-20)
- Complex payload validation
- Structural checks for nested objects
- User-specific cart filtering
- Edge case handling for deletions

---

## ⚠️ Important Notes
1. Test #6 and #10 use filter parameters not natively supported by FakeStoreAPI
2. Test #20 assumes pre-existing carts for user ID 5
3. Negative ID tests (#12,18) validate error handling
4. All timestamps hardcoded to `2020-03-02` for consistency

---
