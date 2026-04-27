
# Bug Reports - E-commerce Testing (SauceDemo)

**Tested Application**: https://www.saucedemo.com/

| Bug ID | Test Case ID | Bug Title                              | Severity | Steps to Reproduce                                                                 | Expected Result                          | Actual Result                              | Screenshot                  | Status    |
|--------|--------------|----------------------------------------|----------|------------------------------------------------------------------------------------|------------------------------------------|--------------------------------------------|-----------------------------|-----------|
| BUG_001 | TC_LOGIN_002 | Error message is not user-friendly     | Medium   | 1. Go to login page<br>2. Enter wrong password<br>3. Click Login                   | Clear and polite error message           | Technical error message shown              | login-error.png             | Open      |
| BUG_002 | TC_LOGIN_005 | Password field does not show "required" error clearly | Low     | 1. Enter username<br>2. Leave password empty<br>3. Click Login                     | Clear message "Password is required"     | Generic error message                      | password-empty.png          | Open      |
| BUG_003 | TC_PRODUCT_001 | Cart icon count updates slowly         | Low      | 1. Login<br>2. Add multiple items quickly                                          | Cart count updates instantly             | Delay in updating cart count               | cart-delay.png              | Open      |

### Notes:
- All bugs were found during manual testing.
- Screenshots are stored in the `Screenshots/` folder.
- I will add more bugs as I continue testing.

**Total Bugs Found**: 3 (as of now)
