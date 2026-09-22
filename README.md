## 🏫 Academic Context
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=for-the-badge&logo=pydantic&logoColor=white)
![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)

**Student Status:** Computer Science (L3 Student)  
**Context:** Hands-on training project following a Coursera API Development course  
**Objective:** Building a complete RESTful Web API with OAuth2 security, nested Pydantic data validation, dynamic Streamlit interface, and automated Postman integration testing.

---

## 📖 Repository Overview

This repository serves as a practical implementation project for web services architecture and backend development. It contains a fully functional **FastAPI** backend providing CRUD operations for managing books and authors, accompanied by an interactive **Streamlit** dashboard and automated testing suites.

## 🧠 Key Concepts Explored

### 1. RESTful API Architecture & CRUD

* **Verb Mapping:** Implementing standard HTTP methods (`GET`, `POST`, `PUT`, `DELETE`) for complete resource lifecycle management.
* **Path & Query Parameters:** Routing requests effectively to retrieve specific books or filter collections dynamically.
* **HTTP Response Codes:** Returning standard status codes (`200 OK`, `201 Created`, `400 Bad Request`, `401 Unauthorized`, `404 Not Found`) for predictable client interaction.

### 2. Data Validation & Schemas (Pydantic)

* **Nested Models:** Defining complex data relations through nested Pydantic classes (`Book` schema referencing an `Author` schema).
* **Type Safety & Email Validation:** Enforcing strict type checking using `int`, `str`, `bool`, and `EmailStr` rules on incoming requests.
* **Serialization:** Leveraging `.model_dump()` for seamless conversion between Python objects and JSON models.

### 3. Authentication & Security (OAuth2)

* **Bearer Token Flow:** Securing write endpoints (`POST`, `PUT`, `DELETE`) using `OAuth2PasswordBearer` and form authentication via `/token`.
* **Dependency Injection:** Utilizing FastAPI's `Depends()` mechanism to protect routes and verify token validity before executing endpoints.

### 4. Reactive Frontend (Streamlit)

* **API Consumption:** Integrating `requests` library to fetch and push JSON payloads to backend REST routes.
* **Session State Management:** Storing Bearer tokens inside `st.session_state` to keep users logged in across reruns.
* **Form Control:** Securing input workflows via `st.form` to optimize request timing and UI reactivity.

### 5. API Testing & Documentation

* **OpenAPI & Swagger UI:** Utilizing auto-generated docs at `/docs` for real-time endpoint testing and schema inspection.
    * **Automated Postman Workflows:** Executing chained end-to-end integration tests (*Create* --> *Retrieve* --> *Update* --> *Delete*) using Postman script assertions.

## 🛠️ Technical Summary

| Endpoint / File | Concept Applied | Purpose |
| :--- | :--- | :--- |
| `POST /token` | `OAuth2PasswordBearer`, Form Data | Authenticates user credentials and issues Bearer tokens. |
| `GET /books` | `RESTful GET`, JSON Response | Retrieves and lists all available books in the system. |
| `POST /books` | `Pydantic Validation`, Protected Route | Validates payload against `Book` model and adds a new item. |
| `GET /books/{id}` | `Path Parameters`, Error Handling | Fetches details for a single book or returns `404 Not Found`. |
| `PUT /books/{id}` | `State Modification`, Authentication | Updates existing book and nested author details. |
| `DELETE /books/{id}` | `Resource Removal`, Security | Deletes a specified book from memory using Bearer token verification. |
| `GET /authors` | `Nested Data Query` | Filters and retrieves specific author details across book collections. |
| **Streamlit App** | `st.session_state`, `requests` | Provides a web UI consuming the backend REST API endpoints. |
| **Postman Suite** | `pm.test()`, Automated Integration | Verifies complete API lifecycle (*Create* $\rightarrow$ *Retrieve* $\rightarrow$ *Update* $\rightarrow$ *Delete*). |

---

*Built with curiosity during my L3 Computer Science journey to put into practice backend security, APIs, and reactive UIs learned through online training.*
