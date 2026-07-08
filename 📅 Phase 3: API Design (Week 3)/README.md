# 📅 Phase 3: API Design (Week 3)

Learn how to design clean, scalable, and maintainable REST APIs using Django REST Framework (DRF). This phase covers API conventions, query parameters, versioning, and best practices.

---

# 📚 Topics to Learn

- REST API Best Practices
- HTTP Methods
- API Endpoints
- Pagination
- Filtering
- Sorting
- Searching
- API Versioning

---

# 1️⃣ REST API Best Practices

A REST (Representational State Transfer) API is a standard way for clients (web browsers, mobile apps, etc.) to communicate with a server using HTTP.

A REST API should:

- Use meaningful resource names
- Use proper HTTP methods
- Return appropriate HTTP status codes
- Return data in JSON format
- Be stateless
- Support filtering, searching, sorting, and pagination

---

# 2️⃣ HTTP Methods

## GET

Retrieve data from the server.

### Example

```http
GET /products
```

### Response

```json
[
    {
        "id": 1,
        "name": "Laptop",
        "price": 65000
    },
    {
        "id": 2,
        "name": "Mouse",
        "price": 800
    }
]
```

---

## POST

Create a new resource.

### Example

```http
POST /products
```

### Request Body

```json
{
    "name": "Keyboard",
    "price": 1200
}
```

### Response

```json
{
    "id": 3,
    "name": "Keyboard",
    "price": 1200
}
```

---

## PUT

Update an existing resource.

### Example

```http
PUT /products/5
```

### Request Body

```json
{
    "name": "Gaming Keyboard",
    "price": 2500
}
```

---

## DELETE

Delete a resource.

### Example

```http
DELETE /products/5
```

### Response

```http
204 No Content
```

---

# 3️⃣ Pagination

Pagination divides large datasets into smaller pages to improve performance.

## Example

```http
GET /products?page=1&limit=10
```

### Meaning

- Page = 1
- Show only 10 products

### Response

```json
{
    "count": 100,
    "next": "/products?page=2&limit=10",
    "previous": null,
    "results": [
        ...
    ]
}
```

### Benefits

- Faster response
- Lower memory usage
- Better user experience

---

# 4️⃣ Filtering

Filtering returns only records that match specific conditions.

## Example

```http
GET /products?category=laptop
```

### Another Example

```http
GET /products?brand=Apple
```

### Another Example

```http
GET /products?price_lt=50000
```

### Benefits

- Reduce unnecessary data
- Faster API responses

---

# 5️⃣ Sorting

Sorting arranges records in ascending or descending order.

## Sort by Price

```http
GET /products?sort=price
```

### Sort by Name

```http
GET /products?sort=name
```

### Descending Order

```http
GET /products?sort=-price
```

The minus (`-`) indicates descending order.

---

# 6️⃣ Searching

Searching allows users to find records using keywords.

## Example

```http
GET /products?q=iphone
```

### Example Response

```json
[
    {
        "id": 5,
        "name": "iPhone 16",
        "price": 85000
    }
]
```

---

# 7️⃣ API Versioning

API versioning allows you to introduce changes without breaking existing clients.

## Version 1

```http
/api/v1/products
```

## Version 2

```http
/api/v2/products
```

### Why Version APIs?

- Maintain backward compatibility
- Add new features safely
- Support older mobile/web applications

---

# REST API Example

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/products` | Get all products |
| GET | `/products/5` | Get product by ID |
| POST | `/products` | Create a product |
| PUT | `/products/5` | Update a product |
| DELETE | `/products/5` | Delete a product |

---

# API Request Flow

```text
Client (Browser / Mobile App)
            │
            ▼
      HTTP Request
            │
            ▼
Django REST Framework API
            │
            ▼
     Business Logic
            │
            ▼
      PostgreSQL Database
            │
            ▼
      JSON Response
            │
            ▼
Client
```

---

# Best Practices Checklist

- Use nouns instead of verbs in URLs.
- Keep URLs simple and meaningful.
- Always return JSON responses.
- Use appropriate HTTP status codes.
- Validate incoming request data.
- Implement pagination for large datasets.
- Support filtering, sorting, and searching.
- Secure APIs using authentication and authorization.
- Version APIs to avoid breaking changes.
- Write clear API documentation.

---

# Technologies Used

- Python
- Django
- Django REST Framework (DRF)
- PostgreSQL
- JSON
- HTTP

---

# Summary

By the end of this phase, you should be able to:

- Design RESTful APIs
- Perform CRUD operations
- Use HTTP methods correctly
- Implement pagination
- Filter API results
- Sort data
- Search resources
- Version your APIs
- Build production-ready REST APIs using Django REST Framework
