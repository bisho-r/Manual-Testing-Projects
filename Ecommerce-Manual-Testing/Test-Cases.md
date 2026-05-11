# Manual Test Cases - E-commerce Website (SauceDemo)

**Tested Application**: https://www.saucedemo.com/

**Tested By**: Bishwanath Rana  
**Date**: April 2026

**Objective:** Perform complete functional, negative, boundary, regression, usability, and non-functional testing.

---

## Table of Contents
- [1. Login Module (TC_001 – TC_020)](#1-login-module)
- [2. Products / Inventory Module (TC_021 – TC_045)](#2-products-inventory-module)
- [3. Cart Module (TC_046 – TC_065)](#3-cart-module)
- [4. Checkout Module (TC_066 – TC_095)](#4-checkout-module)
- [5. Others / Non-Functional / Regression (TC_096 – TC_110)](#5-others--non-functional--regression)

---

### 1. Login Module (TC_001 – TC_020)

| TC_ID      | Test Scenario                                   | Preconditions          | Test Steps                                                                 | Test Data                              | Expected Result |
|------------|-------------------------------------------------|------------------------|----------------------------------------------------------------------------|----------------------------------------|-----------------|
| TC_001    | Successful login - Standard User               | On login page         | 1. Enter username<br>2. Enter password<br>3. Click Login                 | standard_user / secret_sauce          | Redirected to Products page |
| TC_002    | Successful login - Problem User                | On login page         | 1-3 same as above                                                         | problem_user / secret_sauce           | Products page loads with broken images |
| TC_003    | Successful login - Performance Glitch User     | On login page         | 1-3 same as above                                                         | performance_glitch_user / secret_sauce| Products page loads slowly |
| TC_004    | Successful login - Locked Out User             | On login page         | 1-3 same as above                                                         | locked_out_user / secret_sauce        | Error: "Sorry, this user has been locked out." |
| TC_005    | Invalid Username                               | On login page         | Invalid username + valid password                                         | wronguser / secret_sauce              | Error: "Username and password do not match" |
| TC_006    | Invalid Password                               | On login page         | Valid username + invalid password                                         | standard_user / wrongpass             | Error: "Username and password do not match" |
| TC_007    | Empty Username                                 | On login page         | Leave username blank + enter password                                     | (blank) / secret_sauce                | "Username is required" |
| TC_008    | Empty Password                                 | On login page         | Enter username + leave password blank                                     | standard_user / (blank)               | "Password is required" |
| TC_009    | Empty Username & Password                      | On login page         | Both fields blank                                                         | (blank) / (blank)                     | Both error messages shown |
| TC_010    | Case Sensitivity Check - Username              | On login page         | Enter username in different case                                          | STANDARD_USER / secret_sauce          | Login fails |
| TC_011    | Case Sensitivity Check - Password              | On login page         | Correct username + wrong case password                                    | standard_user / SECRET_SAUCE          | Login fails |
| TC_012    | SQL Injection Attempt                          | On login page         | Enter SQL query in username field                                         | ' OR '1'='1 / secret_sauce            | Treated as normal text, login fails |
| TC_013    | XSS Attack Attempt                             | On login page         | Enter script tag in username/password                                     | <script>alert(1)</script>             | No alert, treated as text |
| TC_014    | Login after successful Logout                  | Logged in             | Logout → Login again                                                      | standard_user / secret_sauce          | Successful login |
| TC_015    | Browser Back Button after Login                | Logged in             | Click browser back button                                                 | -                                      | Remains on Products page |
| TC_016    | Multiple Failed Login Attempts                 | On login page         | Enter wrong password 5 times                                              | standard_user / wrong                 | No lockout (app behavior) |
| TC_017    | Logout Functionality                           | Logged in             | Open menu → Click Logout                                                  | -                                      | Redirected to login page |
| TC_018    | Login with Special Characters in Password      | On login page         | Use special characters                                                    | standard_user / secret@sauce#123      | Error message |
| TC_019    | Redirect URL after Login                       | On login page         | Successful login                                                          | standard_user / secret_sauce          | URL contains `/inventory.html` |
| TC_020    | Password Visibility Toggle                     | On login page         | Click eye icon (if available)                                             | -                                      | Password shows/hides |

---

### 2. Products / Inventory Module (TC_021 – TC_045)

| TC_ID      | Test Scenario                                      | Preconditions              | Test Steps                                                                 | Test Data                    | Expected Result |
|------------|----------------------------------------------------|----------------------------|----------------------------------------------------------------------------|------------------------------|-----------------|
| TC_021    | Verify all 6 products are displayed               | Logged in                 | Login → Observe products grid                                             | standard_user                | Exactly 6 products visible |
| TC_022    | Verify all product images load                    | On Products page          | Check each product image                                                  | -                            | No broken images |
| TC_023    | Verify product name, description & price          | On Products page          | Validate details of all products                                          | -                            | All information correct |
| TC_024    | Add single item to cart                           | On Products page          | Click "Add to cart" on one product                                        | Sauce Labs Backpack          | Cart badge updates to 1 |
| TC_025    | Add multiple items to cart                        | On Products page          | Add 3 different products                                                  | -                            | Cart badge shows correct count |
| TC_026    | Remove item from Products page                    | Item added                | Click "Remove" button                                                     | -                            | Cart badge decreases |
| TC_027    | Sort by Name (A to Z)                             | On Products page          | Select "Name (A to Z)" from dropdown                                      | -                            | Products sorted A to Z |
| TC_028    | Sort by Name (Z to A)                             | On Products page          | Select "Name (Z to A)"                                                    | -                            | Products sorted Z to A |
| TC_029    | Sort by Price (Low to High)                       | On Products page          | Select "Price (low to high)"                                              | -                            | Lowest price first |
| TC_030    | Sort by Price (High to Low)                       | On Products page          | Select "Price (high to low)"                                              | -                            | Highest price first |
| TC_031    | Open Product Detail page                          | On Products page          | Click on any product name                                                 | -                            | Product detail page opens |
| TC_032    | Add item from Product Detail page                 | On detail page            | Click "Add to cart"                                                       | -                            | Item added, badge updates |
| TC_033    | Back to Products button                           | On detail page            | Click "Back to products"                                                  | -                            | Returns to inventory page |
| TC_034    | "Add to cart" button changes to "Remove"          | On Products page          | Add item → check button text                                              | -                            | Button text changes |
| TC_035    | Reset App State                                   | Items in cart             | Menu → Reset App State                                                    | -                            | Cart becomes empty |
| TC_036    | Responsive Design - Mobile View                   | On Products page          | Resize window to mobile size                                              | -                            | Layout adjusts properly |
| TC_037    | Verify Footer Social Links                        | On Products page          | Click Twitter, Facebook, LinkedIn                                         | -                            | Links open in new tabs |
| TC_038    | Verify Page Title                                 | On Products page          | Check browser tab title                                                   | -                            | Title is correct |
| TC_039    | Performance Check with Glitch User                | Login as glitch user      | Observe loading time                                                      | performance_glitch_user      | Noticeable delay |
| TC_040    | Verify Product Count remains 6 after sorting      | On Products page          | Sort items                                                                | -                            | Still 6 products |

---

### 3. Cart Module (TC_046 – TC_065)

| TC_ID      | Test Scenario                                      | Preconditions           | Test Steps                                                                 | Test Data               | Expected Result |
|------------|----------------------------------------------------|-------------------------|----------------------------------------------------------------------------|-------------------------|-----------------|
| TC_046    | Added items appear in Cart                        | Items added             | Add items → Click cart icon                                               | 2+ items                | Items displayed correctly |
| TC_047    | Verify quantity, price & subtotal                 | Items in cart           | Check values in cart                                                      | -                       | Correct values shown |
| TC_048    | Remove item from Cart                             | Items in cart           | Click Remove button                                                       | -                       | Item removed successfully |
| TC_049    | Continue Shopping button                          | On Cart page            | Click "Continue Shopping"                                                 | -                       | Redirected to Products page |
| TC_050    | Cart persists after page refresh                  | Items in cart           | Refresh browser                                                           | -                       | Items still present |
| TC_051    | Cart persists after logout & login                | Items in cart           | Logout → Login again                                                      | standard_user           | Items remain |
| TC_052    | Empty Cart Message                                | No items in cart        | Go to cart                                                                | Empty cart              | "Your cart is empty" shown |
| TC_053    | Checkout button enabled                           | Items in cart           | Check Checkout button                                                     | -                       | Button is enabled |
| TC_054    | Checkout button disabled when cart empty          | Empty cart              | Check Checkout button                                                     | -                       | Button is disabled |
| TC_055    | Cart badge updates after removal                  | Items in cart           | Remove item                                                               | -                       | Badge count decreases |

---

### 4. Checkout Module (TC_066 – TC_095)

| TC_ID      | Test Scenario                                      | Preconditions                | Test Steps                                                                 | Test Data                          | Expected Result |
|------------|----------------------------------------------------|------------------------------|----------------------------------------------------------------------------|------------------------------------|-----------------|
| TC_066    | Navigate to Checkout Information                  | Items in cart               | Cart → Click Checkout                                                     | 2 items                            | Information page opens |
| TC_067    | First Name Required Validation                    | On Information page         | Leave First Name blank → Continue                                         | -                                  | "First Name is required" |
| TC_068    | Last Name Required Validation                     | On Information page         | Leave Last Name blank → Continue                                          | -                                  | "Last Name is required" |
| TC_069    | Zip/Postal Code Required Validation               | On Information page         | Leave Zip blank → Continue                                                | -                                  | "Postal Code is required" |
| TC_070    | Proceed with Valid Information                    | On Information page         | Fill all fields → Continue                                                | Bishor / Rana / 12345              | Goes to Overview page |
| TC_071    | Verify Order Summary                              | On Overview page            | Check items, quantity, description, price                                 | -                                  | All details match |
| TC_072    | Verify Tax (8%) and Total Calculation             | On Overview page            | Check calculations                                                        | -                                  | Correct tax & total |
| TC_073    | Complete Purchase                                 | On Overview page            | Click Finish                                                              | -                                  | Order placed |
| TC_074    | Thank You / Order Confirmation Page               | After Finish                | Observe page                                                              | -                                  | "Thank you for your order!" |
| TC_075    | Back to Home button                               | On Thank You page           | Click "Back to products"                                                  | -                                  | Redirected to Products |
| TC_076    | Cancel Checkout from Information page             | On Information page         | Click Cancel                                                              | -                                  | Returns to Cart |
| TC_077    | Cancel Checkout from Overview page                | On Overview page            | Click Cancel                                                              | -                                  | Returns to Cart |

---

### 5. Others / Non-Functional / Regression (TC_096 – TC_110)

| TC_ID      | Test Scenario                                      | Preconditions     | Test Steps                                      | Test Data      | Expected Result |
|------------|----------------------------------------------------|-------------------|-------------------------------------------------|----------------|-----------------|
| TC_096    | Keyboard Navigation (Accessibility)               | Any page          | Use Tab key to navigate                        | -              | All elements accessible |
| TC_097    | Responsive Design - Multiple Screen Sizes         | All pages         | Resize browser window                          | -              | UI remains usable |
| TC_098    | Cross Browser Compatibility                       | Critical flows    | Test on Chrome & Firefox                       | -              | Consistent behavior |
| TC_099    | No sensitive data in URL                          | After login       | Check URL                                      | -              | No credentials in URL |
| TC_100    | End-to-End Flow                                   | Fresh session     | Login → Add items → Checkout → Order           | -              | Complete flow successful |
| TC_101    | Page Title Validation                             | All major pages   | Check browser title                            | -              | Correct titles |
| TC_102    | Footer Links Working                              | Any page          | Click social links                             | -              | Open correctly |
| TC_103    | Regression Testing - Critical Flows               | After changes     | Run Login + Checkout flow                      | -              | All pass |
| TC_104    | Performance Observation                           | Products page     | Note load time                                 | -              | Reasonable speed |
| TC_105    | HTTPS Security                                    | All pages         | Check connection                               | -              | Secure (HTTPS) |                                             |

**Notes**: 
- I executed these test cases manually.
- Screenshots of passed/failed cases will be added in the Screenshots folder.
- More test cases (Checkout, Filter, etc.) will be added soon.
