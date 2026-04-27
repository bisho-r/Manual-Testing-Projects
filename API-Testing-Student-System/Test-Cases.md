# REST API Testing - Student / User Management (reqres.in)

Tested API: https://reqres.in/

**Tools Used**: Postman (Manual Testing)

### Test Cases

| Test Case ID       | Test Scenario                    | Test Steps                                      | Test Data                          | Expected Result                                      |
|--------------------|----------------------------------|-------------------------------------------------|------------------------------------|------------------------------------------------------|
| TC_API_001        | Get Single User (GET)           | Send GET request to /api/users/2                | -                                  | Status 200 + user data returned                      |
| TC_API_002        | Create New User (POST)          | Send POST request to /api/users                 | {"name": "Bishwanath", "job": "QA Intern"} | Status 201 + user created with id and timestamp     |
| TC_API_003        | Update User (PUT)               | Send PUT request to /api/users/2                | {"name": "Bishwanath", "job": "QA Tester"} | Status 200 + updated data returned                   |
| TC_API_004        | Delete User (DELETE)            | Send DELETE request to /api/users/2             | -                                  | Status 204 (No Content)                              |
| TC_API_005        | Invalid User ID                 | Send GET request to /api/users/9999             | -                                  | Status 404 + error response                          |
| TC_API_006        | Register Successful             | POST to /api/register                           | Valid email & password             | Status 200 + token returned                          |

**Notes**:
- All requests were tested manually using Postman.
- Response validation included status codes, response time, and JSON structure.
- Screenshots of successful and failed requests are in the Screenshots folder.
