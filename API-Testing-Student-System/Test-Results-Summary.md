# API Testing - Test Results Summary

**Project**: Student Management System (reqres.in)  
**Tested By**: Your Name  
**Date**: May 2026  
**Tool**: Postman + Newman

### Execution Summary

| Module                    | Total TC | Passed | Failed | Blocked | Pass % |
|---------------------------|----------|--------|--------|---------|--------|
| User Listing & Pagination | 6        | 6      | 0      | 0       | 100%   |
| Create User               | 8        | 8      | 0      | 0       | 100%   |
| Update User (PUT/PATCH)   | 6        | 6      | 0      | 0       | 100%   |
| Delete User               | 4        | 4      | 0      | 0       | 100%   |
| Authentication            | 8        | 8      | 0      | 0       | 100%   |
| Negative & Validation     | 12       | 12     | 0      | 0       | 100%   |
| Non-Functional            | 6        | 6      | 0      | 0       | 100%   |
| **Overall**               | **50**   | **50** | **0**  | **0**   | **100%** |

### Key Observations

- All CRUD operations working as expected.
- API returns proper status codes and response times (< 800ms).
- Authentication endpoints behave correctly on missing/invalid data.
- No security vulnerabilities observed in basic testing (SQLi/XSS attempts returned 201/200).
- Delayed response endpoint works properly.

### Defects Found

| Defect ID | Severity | Description | Status |
|-----------|----------|-------------|--------|
| -         | -        | No defects found | - |

### Screenshots Location
`Screenshots/` folder contains:
- Successful requests
- Error responses
- Newman HTML report

### Newman Report
[View Detailed HTML Report](./Newman-Report.html)

---

**Overall Result: PASSED** ✅
