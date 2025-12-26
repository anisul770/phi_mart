
---

# 🛒 PhiMart – E-commerce REST API

PhiMart is a **Django REST Framework–based e-commerce backend** that provides a complete set of APIs for **user authentication, product management, cart & order processing**, and **role-based access control**.

The project uses **JWT authentication with Djoser**, follows **clean service-based architecture**, and includes **interactive API documentation via Swagger**.

---

## 🚀 Features

### 🔐 Authentication & Users

* JWT Authentication (Access & Refresh tokens)
* User registration, login, logout
* Custom User model
* Role-based permissions (Admin / Authenticated User)

### 📦 Products

* Product CRUD operations
* Product images support
* Validation & custom permissions
* Category-like separation handled via product logic

### 🛒 Orders

* Order creation and listing
* Order items with total price calculation
* Service layer (`services.py`) for business logic
* Secure user-specific order access

### 🧩 Architecture

* Clean separation of concerns
* Service layer for complex logic
* Custom permissions
* Fixtures for sample product data

### 📘 Documentation

* Swagger UI
* ReDoc UI
* Fully documented endpoints

---

## 🛠 Tech Stack

* **Backend:** Django, Django Rest Framework
* **Authentication:** Djoser + JWT
* **Database:** SQLite (development)
* **API Docs:** drf-yasg (Swagger / ReDoc)
* **Language:** Python 3

---

## 📂 Project Structure

```
PhiMart/
├── api/                 # Shared API utilities & permissions
├── users/               # Custom user model & auth APIs
├── product/             # Product management
├── order/               # Order & order item logic
├── fixtures/            # Initial product data
├── media/               # Uploaded product images
├── phi_mart/            # Project settings & URLs
├── manage.py
├── requirements.txt
└── README.md
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/anisul770/phi_mart.git
cd phi_mart
```

---

### 2️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate      # Windows
```

---

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4️⃣ Run Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

---

### 5️⃣ Load Sample Data (Optional)

```bash
python manage.py loaddata fixtures/product_data.json
```

---

### 6️⃣ Create Superuser

```bash
python manage.py createsuperuser
```

---

### 7️⃣ Run Development Server

```bash
python manage.py runserver
```

Server runs at:

```
http://127.0.0.1:8000/
```

---

## 🔐 Authentication (JWT)

PhiMart uses **Djoser + SimpleJWT**.

### Auth Endpoints

| Action        | Endpoint             |
| ------------- | -------------------- |
| Register      | `/auth/users/`       |
| Login         | `/auth/jwt/create/`  |
| Refresh Token | `/auth/jwt/refresh/` |
| Logout        | `/auth/jwt/logout/`  |
| Current User  | `/auth/users/me/`    |

### Authorization Header

```
Authorization: Bearer <access_token>
```

---

## 📦 Product API

```
GET    /api/products/
GET    /api/products/{id}/
POST   /api/products/
PATCH  /api/products/{id}/
DELETE /api/products/{id}/
```

🔒 Create / Update / Delete → **Admin only**

---

## 🛒 Order API

```
GET    /api/orders/
POST   /api/orders/
GET    /api/orders/{id}/
```

* Orders are **user-specific**
* Total price is calculated automatically
* Business logic handled via `order/services.py`

---

## 📘 API Documentation

### Swagger UI

```
http://127.0.0.1:8000/swagger/
```

### ReDoc

```
http://127.0.0.1:8000/redoc/
```


## 🔒 Permissions & Security

* JWT-based authentication
* Custom permission classes
* Users can only access **their own orders**
* Admin users manage products

---

## 📌 Future Improvements

* Cart API separation
* Payment gateway integration
* Product reviews & ratings
* Wishlist functionality

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**ANISUL HAQUE**
Backend Developer | Django & DRF
📍 Italy

---
[LinkedIn](https://www.linkedin.com/in/anisul770/)
