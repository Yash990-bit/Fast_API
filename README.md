# 🚀 FastAPI Backend

A modern, high-performance backend built with **FastAPI**. This project provides REST APIs with automatic documentation, validation, authentication support, and scalable architecture.

---

# 📌 Features

- ⚡ High-performance FastAPI framework
- 📖 Automatic Swagger & ReDoc documentation
- 🔒 JWT Authentication (Optional)
- 🗄️ Database Integration (SQLAlchemy)
- 📦 Pydantic Data Validation
- 🌍 CORS Support
- 📝 Logging
- 🔄 Environment Variable Support
- 🛠️ Modular Folder Structure
- 🚀 Easy Deployment

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| FastAPI | Backend Framework |
| Python | Programming Language |
| SQLAlchemy | ORM |
| Pydantic | Data Validation |
| Uvicorn | ASGI Server |
| JWT | Authentication |
| SQLite / PostgreSQL | Database |
| Alembic | Database Migration |
| python-dotenv | Environment Variables |

---

# 📂 Project Structure

```
fastapi-project/
│
├── app/
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   ├── crud.py
│   ├── auth.py
│   ├── dependencies.py
│   │
│   ├── routers/
│   │     ├── user.py
│   │     ├── auth.py
│   │     └── product.py
│   │
│   └── utils/
│         ├── hashing.py
│         └── token.py
│
├── requirements.txt
├── .env
├── README.md
└── .gitignore
```

---

# ⚙️ Installation

## 1. Clone Repository

```bash
git clone https://github.com/yourusername/fastapi-project.git

cd fastapi-project
```

---

## 2. Create Virtual Environment

### Windows

```bash
python -m venv venv

venv\Scripts\activate
```

### Linux / Mac

```bash
python3 -m venv venv

source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Configure Environment Variables

Create a **.env** file.

```env
DATABASE_URL=sqlite:///./test.db

SECRET_KEY=your_secret_key

ALGORITHM=HS256

ACCESS_TOKEN_EXPIRE_MINUTES=30
```

---

# ▶️ Running the Server

```bash
uvicorn app.main:app --reload
```

Server will start at

```
http://127.0.0.1:8000
```

---

# 📚 API Documentation

FastAPI automatically generates API documentation.

### Swagger UI

```
http://127.0.0.1:8000/docs
```

### ReDoc

```
http://127.0.0.1:8000/redoc
```

---

# 📦 Example API

## GET Request

```http
GET /users
```

Response

```json
[
    {
        "id":1,
        "name":"John"
    }
]
```

---

## POST Request

```http
POST /users
```

Body

```json
{
    "name":"John",
    "email":"john@gmail.com"
}
```

Response

```json
{
    "id":1,
    "name":"John",
    "email":"john@gmail.com"
}
```

---

# 🗄️ Database Migration (Alembic)

Initialize Alembic

```bash
alembic init alembic
```

Create Migration

```bash
alembic revision --autogenerate -m "Initial Migration"
```

Upgrade Database

```bash
alembic upgrade head
```

---

# 📦 requirements.txt

```txt
fastapi
uvicorn
sqlalchemy
pydantic
python-dotenv
python-jose
passlib
bcrypt
alembic
psycopg2-binary
```

---

# 🚀 Deployment

Run using Uvicorn

```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

Docker

```dockerfile
FROM python:3.11

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt

CMD ["uvicorn","app.main:app","--host","0.0.0.0","--port","8000"]
```

Build

```bash
docker build -t fastapi-app .
```

Run

```bash
docker run -p 8000:8000 fastapi-app
```

---

# 🧪 Testing

Run tests using pytest

```bash
pytest
```

---

# 🔐 Authentication Flow

```
User Login
      │
      ▼
Validate Credentials
      │
      ▼
Generate JWT Token
      │
      ▼
Client Stores Token
      │
      ▼
Token Sent in Authorization Header
      │
      ▼
Protected API Access
```

Authorization Header

```
Authorization: Bearer <JWT_TOKEN>
```

---

# 📈 Future Improvements

- OAuth Login
- Email Verification
- Redis Caching
- Docker Compose
- CI/CD Pipeline
- Unit Testing
- Role-Based Access Control (RBAC)
- Background Tasks
- WebSocket Support

---

# 🤝 Contributing

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature-name
```

3. Commit changes

```bash
git commit -m "Added new feature"
```

4. Push

```bash
git push origin feature-name
```

5. Open a Pull Request

---

# 📄 License

This project is licensed under the MIT License.

---

# 👨‍💻 Author

**Your Name**

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile
