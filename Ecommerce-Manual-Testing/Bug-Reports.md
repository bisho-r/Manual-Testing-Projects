
# Bug Reports - E-commerce Testing (SauceDemo)

**Tested Application**: https://www.saucedemo.com/

**Tester:** Bishwanath Rana    
**Date:** May 2026  

---

## Bug Summary

| Bug ID | Title | Severity | Priority | Status |
|--------|-------|----------|----------|--------|
| BUG-001 | Cart badge not updating after item removal | Medium | High | Open |
| BUG-002 | Performance glitch user causes extreme delay | Low | Medium | Open |
| BUG-003 | Remove button text does not revert after removal | Low | Medium | Open |
| BUG-004 | Tax calculation inconsistency on Checkout | High | High | Open |
| BUG-005 | Long product description overflows on mobile | Low | Low | Open |
| BUG-006 | Browser back button shows cached authenticated pages | Medium | High | Open |
| BUG-007 | No proper error message for very long input in checkout | Low | Low | Open |
| BUG-008 | Footer social links open in same tab | Low | Low | Open |
| BUG-009 | Sort functionality breaks after Reset App State | Medium | Medium | Open |
| BUG-010 | Cart item quantity not handling multiple additions | Low | Medium | Open |
| BUG-011 | Missing success message animation after order placement | Low | Low | Open |
| BUG-012 | Accessibility - Missing alt text on product images | Low | Low | Open |

---

### Detailed Bug Reports

### **BUG-001**
**Title:** Cart badge count does not update after removing an item from cart  
**Module:** Cart  
**Severity:** Medium | **Priority:** High  
**Steps to Reproduce:**
1. Login as `standard_user`
2. Add 3 products to cart
3. Go to Cart page
4. Remove one item
**Actual Result:** Cart badge still shows 3
**Expected Result:** Cart badge should update to 2
**Environment:** Chrome, Windows 11

---

### **BUG-002**
**Title:** Extreme slow loading with Performance Glitch User  
**Module:** Products Page  
**Severity:** Low | **Priority:** Medium  
**Steps to Reproduce:**
1. Login using `performance_glitch_user`
2. Observe Products page loading
**Actual Result:** Page takes 8–15 seconds to load
**Expected Result:** Page should load within 3–4 seconds
**Environment:** Chrome

---

### **BUG-003**
**Title:** "Remove" button does not change back to "Add to cart" after removal  
**Module:** Products Page  
**Severity:** Low | **Priority:** Medium  
**Steps to Reproduce:**
1. Add an item to cart
2. Click "Remove"
3. Observe button text
**Actual Result:** Button remains as "Remove"
**Expected Result:** Button should change back to "Add to cart"

---

### **BUG-004**
**Title:** Incorrect Tax calculation on Checkout Overview page  
**Module:** Checkout  
**Severity:** High | **Priority:** High  
**Steps to Reproduce:**
1. Add items worth $50+ to cart
2. Proceed to Checkout Overview
**Actual Result:** Tax amount is not consistently 8%
**Expected Result:** Tax should be exactly 8% of item total

---

### **BUG-005**
**Title:** Product description text overflows on mobile view  
**Module:** Products / Detail Page  
**Severity:** Low | **Priority:** Low  
**Steps to Reproduce:**
1. Resize browser to mobile width
2. Check product descriptions
**Actual Result:** Text overflows container
**Expected Result:** Text should wrap properly

---

### **BUG-006**
**Title:** Browser back button allows access to authenticated pages after logout  
**Module:** Authentication  
**Severity:** Medium | **Priority:** High  
**Steps to Reproduce:**
1. Login → Go to Products page
2. Logout
3. Click browser back button
**Actual Result:** Products page is shown again
**Expected Result:** Should redirect to login page

---

### **BUG-007**
**Title:** No character limit validation on Checkout fields  
**Module:** Checkout  
**Severity:** Low | **Priority:** Low  
**Steps to Reproduce:**
1. Go to Checkout Information page
2. Enter 200+ characters in First Name
**Actual Result:** Accepts very long input
**Expected Result:** Should have reasonable character limit

---

### **BUG-008**
**Title:** Social media links in footer open in same tab  
**Module:** Footer  
**Severity:** Low | **Priority:** Low  
**Steps to Reproduce:**
1. Click any social link (Twitter, Facebook, LinkedIn)
**Actual Result:** Opens in same tab
**Expected Result:** Should open in new tab (`target="_blank"`)

---

### **BUG-009**
**Title:** Sorting stops working after using "Reset App State"  
**Module:** Products  
**Severity:** Medium | **Priority:** Medium  
**Steps to Reproduce:**
1. Apply any sort
2. Reset App State
3. Try sorting again
**Actual Result:** Sort does not work properly

---

### **BUG-010**
**Title:** Adding same item multiple times does not increase quantity  
**Module:** Cart  
**Severity:** Low | **Priority:** Medium  
**Steps to Reproduce:**
1. Add same product 3 times from Products page
**Actual Result:** Only 1 item appears in cart
**Expected Result:** Quantity should increase to 3

---

### Notes:
- All bugs were found during manual testing.
- Screenshots are stored in the `Screenshots/` folder.
- I will add more bugs as I continue testing.

**Total Bugs Found**: 10 (as of now)
