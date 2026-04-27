# Manual Test Cases - E-commerce Website (SauceDemo)

**Tested Application**: https://www.saucedemo.com/

**Tested By**: Bishwanath Rana  
**Date**: April 2026

### 1. Login Module Test Cases

| Test Case ID     | Test Scenario                        | Preconditions                  | Test Steps                                                                 | Test Data                              | Expected Result                                                                 |
|------------------|--------------------------------------|--------------------------------|----------------------------------------------------------------------------|----------------------------------------|---------------------------------------------------------------------------------|
| TC_LOGIN_001    | Successful Login - Standard User    | On https://www.saucedemo.com/  | 1. Enter Username<br>2. Enter Password<br>3. Click Login                   | standard_user / secret_sauce          | User successfully logs in and lands on Products page                            |
| TC_LOGIN_002    | Login with Invalid Password         | On login page                  | 1. Enter Username<br>2. Enter wrong password<br>3. Click Login             | standard_user / wrong123              | Error message: "Epic sadface: Username and password do not match any user..."  |
| TC_LOGIN_003    | Login with Empty Username           | On login page                  | 1. Leave username field blank<br>2. Enter password<br>3. Click Login       | (blank) / secret_sauce                | Error: "Epic sadface: Username is required"                                     |
| TC_LOGIN_004    | Login with Empty Password           | On login page                  | 1. Enter username<br>2. Leave password blank<br>3. Click Login             | standard_user / (blank)               | Error: "Epic sadface: Password is required"                                     |
| TC_LOGIN_005    | Login with Locked User              | On login page                  | 1. Enter locked username<br>2. Enter password<br>3. Click Login            | locked_out_user / secret_sauce        | Error: "Epic sadface: Sorry, this user has been locked out."                    |

### 2. Product & Cart Module Test Cases

| Test Case ID     | Test Scenario                        | Preconditions                  | Test Steps                                                                 | Test Data                  | Expected Result                                                                 |
|------------------|--------------------------------------|--------------------------------|----------------------------------------------------------------------------|----------------------------|---------------------------------------------------------------------------------|
| TC_PRODUCT_001  | Add Single Item to Cart             | Logged in as standard_user     | 1. Click "Add to cart" on any product<br>2. Click shopping cart icon       | Any product                | Item count increases to 1 in cart icon                                          |
| TC_CART_001     | Remove Item from Cart               | Item already added to cart     | 1. Go to cart page<br>2. Click "Remove" button                             | One item in cart           | Item is removed and cart becomes empty                                          |
| TC_CART_002     | Continue Shopping from Cart         | On cart page                   | 1. Click "Continue Shopping" button                                        | -                          | User returns to Products page                                                   |

**Notes**: 
- I executed these test cases manually.
- Screenshots of passed/failed cases will be added in the Screenshots folder.
- More test cases (Checkout, Filter, etc.) will be added soon.
