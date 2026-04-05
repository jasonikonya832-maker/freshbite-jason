# FreshBite Delivery System - Testing Guide

## 🧪 Complete Testing & Quality Assurance Guide

This comprehensive guide provides step-by-step instructions to test all features of the delivery system and e-commerce functionality.

---

## ✅ Pre-Testing Checklist

Before starting tests, verify:
- [ ] Website opens without errors
- [ ] All pages load correctly
- [ ] Browser console shows no errors
- [ ] LocalStorage is enabled
- [ ] JavaScript is enabled
- [ ] Using modern browser (Chrome, Firefox, Safari, Edge)

---

## 🛒 **SECTION 1: Shopping Cart Tests**

### Test 1.1: Add Item to Cart
**Steps:**
1. Open `index.html`
2. Click "Shop Now" or go to `products.html`
3. Click "Add to Cart" on any product
4. ✓ Should see: "Added to cart!" notification (green toast)
5. ✓ Cart count should increase in header
6. ✓ Product added to localStorage

**Expected Result:** ✅ Item visible in cart count

---

### Test 1.2: Multiple Items in Cart
**Steps:**
1. Add 3 different products
2. Go to `cart.html`
3. ✓ All 3 items should display
4. ✓ Each with image emoji, name, price, quantity
5. ✓ Cart count shows "3"

**Expected Result:** ✅ All items visible in cart page

---

### Test 1.3: Update Quantity
**Steps:**
1. In cart page, increase quantity of one item to 3
2. ✓ Price should recalculate immediately
3. ✓ Total should update
4. Decrease quantity back to 1
5. ✓ Price updates again

**Expected Result:** ✅ Real-time quantity and price updates

---

### Test 1.4: Remove Item
**Steps:**
1. Click "Remove" button on an item
2. ✓ Item disappears from cart
3. ✓ Cart count decreases
4. ✓ Total recalculates
5. Check cart page refreshes without errors

**Expected Result:** ✅ Item removed successfully

---

### Test 1.5: Empty Cart
**Steps:**
1. Remove all items from cart
2. Go to cart page
3. ✓ Empty cart message displays
4. ✓ "Continue Shopping" button visible
5. Click button, should go to products page

**Expected Result:** ✅ Empty state displays correctly

---

## 🚚 **SECTION 2: Delivery Zone Tests**

### Test 2.1: Display All Zones
**Steps:**
1. Add items to cart
2. Go to checkout: `checkout.html`
3. Fill shipping information:
   - First Name: John
   - Last Name: Doe
   - Email: john@example.com
   - Phone: +254712345678
   - Address: Westlands, Nairobi
   - City: Nairobi
   - Postal Code: 00100
4. ✓ Should see 7 delivery zone cards
5. ✓ Each card shows: Zone name, Fee (KES), Estimated time

**Expected Result:** ✅ All 7 zones display with correct info:
- Central Nairobi: KES 150, 30-45 min
- North Nairobi: KES 200, 45-60 min
- South Nairobi: KES 200, 45-60 min
- East Nairobi: KES 250, 60-75 min
- West Nairobi: KES 200, 45-60 min
- Far North: KES 300, 90-120 min
- Far South: KES 300, 90-120 min

---

### Test 2.2: Select Delivery Zone
**Steps:**
1. Click on "Central Nairobi" card
2. ✓ Card should highlight with orange border
3. ✓ Green checkmark appears on card
4. ✓ Delivery info section appears below
5. ✓ Shows: "Central Nairobi", "KES 150", "30-45 minutes"
6. ✓ Toast notification: "✓ Delivery zone selected..."

**Expected Result:** ✅ Zone selected with visual feedback

---

### Test 2.3: Zone Changes Order Total
**Steps:**
1. Select "Central Nairobi" (KES 150 fee)
2. Look at Order Summary on right
3. ✓ Delivery Fee shows: KES 150
4. ✓ Total includes delivery fee
5. Click "East Nairobi" (KES 250 fee)
6. ✓ Delivery Fee updates to: KES 250
7. ✓ Total recalculates automatically

**Expected Result:** ✅ Total updates when zone changes

---

### Test 2.4: Switch Zones Multiple Times
**Steps:**
1. Select Zone 1 → Check total
2. Select Zone 4 → Check total increases
3. Select Zone 6 → Check total increases again
4. Select Zone 2 → Check total decreases
5. ✓ All calculations correct

**Expected Result:** ✅ Totals correct for all zone changes

---

### Test 2.5: Zone Persists After Refresh
**Steps:**
1. Select a delivery zone
2. Refresh page (F5 or Cmd+R)
3. ✓ Previously selected zone still shows as selected
4. ✓ Delivery info still displays
5. ✓ Correct fee shows in summary

**Expected Result:** ✅ Zone selection persists in localStorage

---

## 💳 **SECTION 3: Payment Method Tests**

### Test 3.1: All Payment Options Available
**Steps:**
1. Scroll to "Payment Method" section
2. Click payment dropdown
3. ✓ Should see 5 options:
   - M-Pesa
   - Airtel Money
   - Credit/Debit Card
   - Bank Transfer
   - 💵 Cash on Delivery (Pay when order arrives)

**Expected Result:** ✅ All 5 payment methods visible

---

### Test 3.2: Select Each Payment Method
**Steps:**
1. Select "M-Pesa"
2. Select "Airtel Money"
3. Select "Credit/Debit Card"
4. Select "Bank Transfer"
5. Select "Cash on Delivery"
6. ✓ Each selection works without errors
7. ✓ Dropdown closes after selection

**Expected Result:** ✅ All payment methods selectable

---

### Test 3.3: Cash on Delivery Text
**Steps:**
1. Open payment method dropdown
2. ✓ Cash on Delivery option shows: "💵 Cash on Delivery (Pay when order arrives)"
3. Select it
4. ✓ Option is clearly marked as COD

**Expected Result:** ✅ COD option clearly identified

---

## 📊 **SECTION 4: Order Summary Tests**

### Test 4.1: Price Calculation Accuracy
**Steps:**
1. Add items totaling KES 1,000
2. ✓ Subtotal: KES 1,000
3. ✓ Tax (16%): KES 160
4. Select zone with KES 150 fee
5. ✓ Total = 1,000 + 160 + 150 = **KES 1,310**

**Expected Result:** ✅ Math is correct

---

### Test 4.2: Multiple Items Pricing
**Steps:**
1. Add 2x Chocolate Cookies (KES 450 each) = KES 900
2. Add 1x Fresh Strawberries (KES 350) = KES 350
3. Subtotal should be: KES 1,250
4. Tax: KES 200 (16% of 1,250)
5. Add delivery fee: KES 150
6. ✓ Total: KES 1,600

**Expected Result:** ✅ Complex calculation correct

---

### Test 4.3: Summary Updates in Real-time
**Steps:**
1. Look at Order Summary on right
2. Change quantity of item in form
3. ✓ Summary should update immediately (reload if needed)
4. Change delivery zone
5. ✓ Summary updates immediately
6. Change payment method
7. ✓ Summary reflects all changes

**Expected Result:** ✅ Summary always accurate

---

## ✔️ **SECTION 5: Order Placement Tests**

### Test 5.1: Form Validation - Missing First Name
**Steps:**
1. Leave "First Name" empty
2. Fill all other fields
3. Select delivery zone
4. Select payment method
5. Click "Place Order"
6. ✓ Should see alert: "Please fill in all shipping information fields"

**Expected Result:** ✅ Validation prevents order

---

### Test 5.2: Form Validation - Missing Address
**Steps:**
1. Fill all fields EXCEPT "Street Address"
2. Select zone and payment
3. Click "Place Order"
4. ✓ Should see validation alert

**Expected Result:** ✅ Validation works for all fields

---

### Test 5.3: Delivery Zone Required
**Steps:**
1. Fill all shipping info
2. Select payment method
3. DO NOT select delivery zone
4. Click "Place Order"
5. ✓ Should see alert: "Please select a delivery zone"

**Expected Result:** ✅ Zone selection enforced

---

### Test 5.4: Payment Method Required
**Steps:**
1. Fill shipping info
2. Select delivery zone
3. DO NOT select payment method
4. Click "Place Order"
5. ✓ Should see alert: "Please select a payment method"

**Expected Result:** ✅ Payment method enforced

---

### Test 5.5: Complete Valid Order - M-Pesa
**Steps:**
1. Fill ALL fields correctly:
   - First Name: John
   - Last Name: Doe
   - Email: john@example.com
   - Phone: +254712345678
   - Address: Westlands, Nairobi
   - City: Nairobi
   - Postal Code: 00100
2. Select "Central Nairobi" delivery zone
3. Select "M-Pesa" payment
4. Click "Place Order"
5. ✓ Should see confirmation page
6. ✓ Should see order number
7. ✓ Should see delivery zone info
8. ✓ Should see delivery time
9. ✓ Should see payment method: "M-PESA"

**Expected Result:** ✅ Order placed successfully

---

### Test 5.6: Complete Valid Order - Cash on Delivery
**Steps:**
1. Fill form completely
2. Select a delivery zone
3. Select "💵 Cash on Delivery"
4. Click "Place Order"
5. ✓ Confirmation shows payment method as "Cash on Delivery"
6. ✓ All other order details correct

**Expected Result:** ✅ COD order confirmed

---

## 📋 **SECTION 6: Order Confirmation Tests**

### Test 6.1: Confirmation Display All Details
**Steps:**
1. Complete an order successfully
2. ✓ Green checkmark icon displays
3. ✓ Title: "Order Confirmed!"
4. ✓ Message about delivery
5. ✓ Order number shown (unique)
6. ✓ Customer name matches
7. ✓ Email address shown
8. ✓ Phone number shown
9. ✓ Delivery address shown
10. ✓ **Delivery Zone shown**
11. ✓ **Estimated Delivery Time shown**
12. ✓ Payment Method shown (M-Pesa, COD, etc.)
13. ✓ Subtotal displayed
14. ✓ Tax displayed
15. ✓ **Delivery Fee displayed**
16. ✓ Total matches calculation

**Expected Result:** ✅ All confirmation details present

---

### Test 6.2: Confirmation with Different Zones
**Steps:**
1. Place order for Central Nairobi
2. ✓ Confirmation shows: "Central Nairobi (CBD, Westlands, Midtown)"
3. ✓ Shows delivery fee: KES 150
4. ✓ Shows time: 30-45 minutes
5. Go back, place new order for East Nairobi
6. ✓ New confirmation shows: East Nairobi
7. ✓ Shows fee: KES 250
8. ✓ Shows time: 60-75 minutes

**Expected Result:** ✅ Correct zone info on each order

---

### Test 6.3: Back to Home Button
**Steps:**
1. On confirmation page
2. Click "Back to Home"
3. ✓ Should navigate to index.html
4. ✓ Cart should be empty
5. ✓ Cart count should be 0

**Expected Result:** ✅ Navigation works, cart cleared

---

## 🔄 **SECTION 7: Data Persistence Tests**

### Test 7.1: Cart Persists Across Sessions
**Steps:**
1. Add 2 items to cart
2. Close browser completely
3. Reopen website
4. ✓ Items still in cart
5. ✓ Quantities preserved
6. ✓ Cart count shows 2

**Expected Result:** ✅ Cart data persists

---

### Test 7.2: Delivery Zone Persists
**Steps:**
1. Go to checkout
2. Select "North Nairobi"
3. Refresh page
4. ✓ North Nairobi still selected
5. ✓ Fee (KES 200) still shows
6. ✓ Time still shows

**Expected Result:** ✅ Zone selection saved

---

### Test 7.3: Order History Saved
**Steps:**
1. Open browser DevTools (F12)
2. Go to Application → LocalStorage
3. Look for "lastOrder"
4. Click it to expand
5. ✓ Should see complete order JSON with:
   - customer info
   - delivery details
   - payment method
   - total amount

**Expected Result:** ✅ Order saved to localStorage

---

## 📱 **SECTION 8: Mobile Responsive Tests**

### Test 8.1: Mobile Checkout View
**Steps:**
1. Open checkout page
2. Resize browser to mobile (375px width)
3. ✓ Zone cards stack vertically
4. ✓ All text readable
5. ✓ Buttons clickable
6. ✓ No horizontal scroll
7. ✓ Form fields properly sized

**Expected Result:** ✅ Mobile layout responsive

---

### Test 8.2: Zone Selection on Mobile
**Steps:**
1. On mobile view
2. Scroll to delivery zones
3. ✓ Cards are full width
4. ✓ Can tap to select
5. ✓ Feedback visible
6. ✓ Info appears below cards

**Expected Result:** ✅ Mobile selection works

---

### Test 8.3: Order Summary on Mobile
**Steps:**
1. On mobile
2. Scroll to Order Summary
3. ✓ Summary visible and readable
4. ✓ All prices shown
5. ✓ Updates with selections
6. ✓ Button (Place Order) is large enough to tap

**Expected Result:** ✅ Summary responsive

---

## 🔀 **SECTION 9: Edge Cases & Error Handling**

### Test 9.1: Very Large Order Total
**Steps:**
1. Add 20 items (all expensive)
2. Go to checkout
3. ✓ Prices calculate correctly
4. ✓ No overflow or display issues
5. ✓ Order can still be placed

**Expected Result:** ✅ Large totals handled

---

### Test 9.2: Browser Back Button
**Steps:**
1. Place an order successfully
2. See confirmation
3. Click browser back button
4. ✓ Should go back safely
5. ✓ No errors in console
6. ✓ Cart is empty

**Expected Result:** ✅ Back navigation works

---

### Test 9.3: Multiple Tab Testing
**Steps:**
1. Open 2 tabs of website
2. Add item in Tab 1
3. Go to products in Tab 2
4. ✓ Tab 1 still has item in cart
5. Add different item in Tab 2
6. ✓ Both tabs sync through localStorage

**Expected Result:** ✅ Data synced across tabs

---

## 🎨 **SECTION 10: Visual & UI Tests**

### Test 10.1: Zone Card Styling
**Steps:**
1. Look at unselected zone cards
2. ✓ Gray border (KES 150/200/250/300 pricing visible
3. ✓ Zone name centered
4. ✓ Time visible
5. Hover over card
6. ✓ Card shadow increases
7. ✓ Border color changes to orange
8. ✓ Card lifts slightly (transform)

**Expected Result:** ✅ Nice hover effects

---

### Test 10.2: Selected Zone Styling
**Steps:**
1. Click to select a zone
2. ✓ Border becomes thick orange (3px)
3. ✓ Green checkmark appears
4. ✓ Background changes to light cream
5. ✓ Info box below shows details

**Expected Result:** ✅ Selected state clear

---

### Test 10.3: Notification Toast
**Steps:**
1. Add item to cart
2. ✓ Green notification appears top-right
3. ✓ Shows "Added to cart!" message
4. ✓ Slides in smoothly
5. ✓ Disappears after 2 seconds
6. Select delivery zone
7. ✓ New notification appears
8. ✓ Shows zone selection message

**Expected Result:** ✅ Notifications work

---

## ✨ **SECTION 11: Feature-Specific Tests**

### Test 11.1: Fee Free Delivery Notice
**Steps:**
1. Go to checkout
2. Below delivery zones
3. ✓ Should see message: "✓ Free delivery for orders over KES 2,000"
4. Read the message

**Expected Result:** ✅ Help text visible

---

### Test 11.2: Delivery Zone Areas Info
**Steps:**
1. Look at zone cards
2. ✓ Each card shows main areas covered
3. Example: "Central Nairobi" → "CBD, Westlands, Midtown"

**Expected Result:** ✅ Area info helps customers

---

### Test 11.3: Order Summary Delivery Line
**Steps:**
1. Select a delivery zone
2. Look at Order Summary
3. ✓ Line shows: "Delivery Fee:" with amount
4. Example: "Delivery Fee: KES 150"
5. Different zones show different amounts

**Expected Result:** ✅ Delivery fee line appears

---

## 📊 **Quick Test Summary Table**

| Section | Tests | Status |
|---------|-------|--------|
| 1. Shopping Cart | 5 | ✅ |
| 2. Delivery Zones | 5 | ✅ |
| 3. Payment Methods | 3 | ✅ |
| 4. Order Summary | 3 | ✅ |
| 5. Order Placement | 6 | ✅ |
| 6. Confirmation | 3 | ✅ |
| 7. Data Persistence | 3 | ✅ |
| 8. Mobile Responsive | 3 | ✅ |
| 9. Edge Cases | 3 | ✅ |
| 10. Visual & UI | 3 | ✅ |
| 11. Feature-Specific | 3 | ✅ |
| **TOTAL** | **42** | ✅ |

---

## 🎯 **Regression Test Checklist**

After any updates, verify:
- [ ] All 7 zones display
- [ ] Zones calculate correct fees
- [ ] Delivery times accurate
- [ ] Zone selection works
- [ ] Totals include delivery fee
- [ ] All 5 payment methods available
- [ ] COD option clear
- [ ] Form validation works
- [ ] Order confirmation shows delivery info
- [ ] Cart persists
- [ ] No console errors
- [ ] Mobile responsive
- [ ] All pages load

---

## 🐛 **Bug Report Template**

If you find an issue, report it as:

**Bug Title:** [Clear one-line description]

**Steps to Reproduce:**
1. [Step 1]
2. [Step 2]
3. [Step 3]

**Expected:** [What should happen]

**Actual:** [What actually happens]

**Screenshots:** [If applicable]

**Browser:** [Chrome/Firefox/Safari/Edge]

**Device:** [Desktop/Mobile/Tablet]

---

## ✅ **Completion Checklist**

After completing all tests, confirm:
- [ ] All 42 tests passed
- [ ] No console errors
- [ ] Mobile version works
- [ ] All calculations accurate
- [ ] Delivery system functional
- [ ] Payment options available
- [ ] Order confirmations display correctly
- [ ] Data persists properly
- [ ] Ready for production

---

**Last Updated:** April 5, 2026  
**Version:** 1.0  
**Status:** Ready for Testing ✅
