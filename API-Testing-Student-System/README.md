# REST API Testing - Student/User Management System

**Tested API**: [https://reqres.in/](https://reqres.in/)

**Tools**: Postman, Newman, JSON Schema Validator, SQL (for conceptual DB validation)

### Scope & Coverage
- **CRUD Operations**
- **Input Validation & Error Handling**
- **Authentication & Authorization** (Register/Login)
- **Response Validation** (Status codes, Schema, Performance)
- **Negative & Edge Case Testing**
- **Database Validation Concepts** (SQL queries)

### Key Test Categories

| Category                  | Coverage                                      | Count |
|--------------------------|-----------------------------------------------|-------|
| Functional (CRUD)        | GET, POST, PUT, PATCH, DELETE                 | 12+   |
| Validation               | Required fields, data types, boundaries       | 15+   |
| Error Handling           | 400, 404, 422, invalid tokens etc.            | 10+   |
| Security Basics          | SQL injection attempts, auth bypass           | 8     |
| Performance              | Response time, load (10 concurrent via Newman)| -     |

**Postman Collection**: [Download](Postman-Collection.json)

**Newman HTML Report**: [View Report](Newman-Report.html)

**View Detailed Test Cases** → [Test-Cases.md](Test-Cases.md) | [Test-Cases.xlsx](Test-Cases.xlsx)
