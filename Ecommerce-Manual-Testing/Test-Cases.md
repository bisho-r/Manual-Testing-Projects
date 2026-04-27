
# Manual Test Cases - E-commerce (SauceDemo)

Tested Website: https://www.saucedemo.com/

| Test Case ID     | Test Scenario                        | Test Steps                                                                 | Test Data                          | Expected Result                                                                 |
|------------------|--------------------------------------|----------------------------------------------------------------------------|------------------------------------|---------------------------------------------------------------------------------|
| TC_LOGIN_001    | Successful Login                     | 1. Go to https://www.saucedemo.com/<br>2. Enter username<br>3. Enter password<br>4. Click Login | standard_user / secret_sauce      | User goes to Products page successfully                                         |
| TC_LOGIN_002    | Login with Wrong Password            | 1. Enter username<br>2. Enter wrong password<br>3. Click Login             | standard_user / wrong123          | Error message appears: "Epic sadface: Username and password do not match..."   |
| TC_LOGIN_003    | Login with Empty Username            | 1. Leave username blank<br>2. Enter password<br>3. Click Login             | (blank) / secret_sauce            | Error message: "Epic sadface: Username is required"                             |
| TC_LOGIN_004    | Login with Locked User               | 1. Enter locked username<br>2. Enter password<br>3. Click Login            | locked_out_user / secret_sauce    | Error: "Epic sadface: Sorry, this user has been locked out."                    |
| TC_PRODUCT_001  | Add Product to Cart                  | 1. Login successfully<br>2. Click "Add to cart" on any product             | Any product                       | Cart icon shows number 1                                                        |
| TC_CART_001     | Remove Item from Cart                | 1. Add item to cart<br>2. Go to cart<br>3. Click Remove                    | One item in cart                  | Item disappears from cart                                                       |

