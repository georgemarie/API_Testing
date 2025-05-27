# 🧪 FakeStoreAPI Postman Test Suite

Comprehensive API testing for [FakeStoreAPI](https://fakestoreapi.com), covering user management, product listings, cart operations, and error handling.

---

## 📦 Setup

1. **Import Collection**  
   - In Postman: *Import → Upload Files →* `API Testing.postman_collection.json`

2. **Environment Variables (Optional)**  
   - Default `base_url` set to `https://fakestoreapi.com`
   - Import environment file if using custom variables

---

## 🚀 Test Coverage

### Users
| #  | Test Case                  | Method | Endpoint            | Status | Validation Criteria                          |
|----|----------------------------|--------|---------------------|--------|----------------------------------------------|
| 1  | ✅ Create Valid User        | POST   | `/users`            | 200    | Returns user ID                              |
| 2  | ❌ Missing Username         | POST   | `/users`            | 400    | Validates required username field            |
| 3  | ❌ Missing Password         | POST   | `/users`            | 400    | Validates required password field            |
| 4  | ❌ No Fields Provided       | POST   | `/users`            | 400    | Empty payload rejection                      |
| 5  | ✅ Get All Users            | GET    | `/users`            | 200    | Returns non-empty array                      |
| 6  | ✅ Filter Users by City     | GET    | `/users?city=San...`| 200    | All users have `address.city = San Antonio`  |

### Authentication
| 7  | ✅ Valid Login              | POST   | `/auth/login`       | 200    | Returns JWT token                            |
| 8  | ❌ Invalid Credentials       | POST   | `/auth/login`       | 401    | Error message: "username or password..."    |

### Products
| 9  | ✅ Get All Products         | GET    | `/products`         | 200    | Non-empty array                              |
| 10 | ✅ Filter by Category       | GET    | `/products?categ...`| 200    | All in `men's clothing` category            |
| 11 | ✅ Get Product by ID        | GET    | `/products/1`       | 200    | Contains `title` field                       |
| 12 | ❌ Invalid Product ID       | GET    | `/products/-1`      | 400    | Error handling for invalid IDs              |

### Carts
| 13 | ✅ Create Cart              | POST   | `/carts`            | 201    | Returns cart ID with products                |
| 14 | ❌ Invalid Cart Items        | POST   | `/carts`            | 400    | Rejects non-integer quantities               |
| 15 | ✅ Get Cart by ID           | GET    | `/carts/1`          | 200    | Validates product structure                  |
| 16 | ❌ Invalid Cart ID          | GET    | `/carts/aa`         | 400    | Error handling for non-numeric IDs          |
| 17 | ✅ Delete Cart              | DELETE | `/carts/1`          | 200    | Successful deletion                          |
| 18 | ❌ Delete Invalid Cart       | DELETE | `/carts/-1`         | 404    | Non-existent cart handling                  |
| 19 | ✅ Get All Carts            | GET    | `/carts`            | 200    | Returns non-empty array                      |
| 20 | ✅ Filter Carts by User     | GET    | `/carts?userId=5`   | 200    | All carts belong to `userId=5`              |

---

## 🔍 Key Test Features
- **Parameterized Filtering**: City (`San Antonio`), Category (`men's clothing`), User ID (`5`)
- **Payload Validation**: Strict type checking for quantity fields
- **Error Messaging**: Specific error responses for failed cases
- **Structural Checks**: Verifies nested object structures (e.g., `address.city`, `products[].productId`)

---

## ⚠️ Important Notes
1. Some endpoints (like city filtering) are **hypothetical implementations** for testing purposes
2. Invalid ID tests use `-1` and `aa` as test values
3. Cart tests assume pre-existing data with `userId=5`
4. Environment variable `base_url` points to production API

---

## 📂 Included Files
- `API Testing.postman_collection.json`
- Environment template (optional)
- `README.md`
