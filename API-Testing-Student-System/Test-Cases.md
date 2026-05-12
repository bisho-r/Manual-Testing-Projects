# API Test Cases - Student/User Management System

**API Base URL**: `https://reqres.in/api`

**Test Environment**: Postman | Newman | Manual

### 1. User Listing & Pagination

| TC_ID | Scenario | Method | Endpoint | Test Data | Expected Status | Expected Result |
|-------|----------|--------|----------|-----------|-----------------|-----------------|
| TC_API_001 | Get all users (default) | GET | `/users` | - | 200 | List of users + pagination |
| TC_API_002 | Get users with page 2 | GET | `/users?page=2` | page=2 | 200 | Users on page 2 |
| TC_API_003 | Get single user | GET | `/users/2` | id=2 | 200 | User details |
| TC_API_004 | Get non-existent user | GET | `/users/9999` | id=9999 | 404 | `{}` (empty) |

### 2. Create User (POST)

| TC_ID | Scenario | Method | Endpoint | Request Body | Expected Status |
|-------|----------|--------|----------|--------------|-----------------|
| TC_API_005 | Create user - Valid | POST | `/users` | `{"name": "Bishwanath Rana", "job": "QA Engineer"}` | 201 |
| TC_API_006 | Create user - Missing name | POST | `/users` | `{"job": "Tester"}` | 201 (name optional) |
| TC_API_007 | Create user - Empty body | POST | `/users` | `{}` | 201 |
| TC_API_008 | Create user - Special characters | POST | `/users` | `{"name": "Test@#$%", "job": "Dev"}` | 201 |

### 3. Update User

| TC_ID | Scenario | Method | Endpoint | Request Body | Expected Status |
|-------|----------|--------|----------|--------------|-----------------|
| TC_API_009 | Update user - PUT (Full) | PUT | `/users/2` | `{"name": "Updated Name", "job": "Senior QA"}` | 200 |
| TC_API_010 | Update user - PATCH (Partial) | PATCH | `/users/2` | `{"job": "Lead QA"}` | 200 |
| TC_API_011 | Update non-existent user | PUT | `/users/9999` | ... | 200 (still returns updated object) |

### 4. Delete User

| TC_ID | Scenario | Method | Endpoint | Expected Status |
|-------|----------|--------|----------|-----------------|
| TC_API_012 | Delete existing user | DELETE | `/users/2` | 204 |
| TC_API_013 | Delete non-existent user | DELETE | `/users/9999` | 204 |

### 5. Authentication & Register/Login

| TC_ID | Scenario | Method | Endpoint | Request Body | Expected Status |
|-------|----------|--------|----------|--------------|-----------------|
| TC_API_014 | Register - Successful | POST | `/register` | `{"email": "eve.holt@reqres.in", "password": "pistol"}` | 200 |
| TC_API_015 | Register - Missing password | POST | `/register` | `{"email": "eve.holt@reqres.in"}` | 400 |
| TC_API_016 | Login - Successful | POST | `/login` | `{"email": "eve.holt@reqres.in", "password": "pistol"}` | 200 |
| TC_API_017 | Login - Invalid credentials | POST | `/login` | `{"email": "eve.holt@reqres.in", "password": "wrong"}` | 400 |

### 6. Negative & Validation Tests

- Invalid HTTP Method (e.g., POST on `/users/2`)
- Invalid JSON format
- Very long name / job title (boundary)
- SQL Injection attempt: `name: "'; DROP TABLE users;--"`
- XSS attempt in name field
- Missing Content-Type header
- Unsupported media type

### 7. Non-Functional

- Response time < 1000ms
- Schema validation (JSON structure)
- Pagination limits
- Delayed response: `/users?delay=3`
