# FabIndia Manual Test Scripts

## User Login & Authentication (Positive & Negative Cases)

### TC_LOGIN_001
**Title**: Mobile Number OTP Login - Happy Path
**Priority**: Critical
**Goal**: Verify users can successfully login using mobile number and OTP
**You Need First**:
- Android/iOS mobile device
- Valid Indian mobile number
- Clear browser cache and cookies

**Test Steps**:
1. Open fabindia.com on mobile browser → Homepage loads within 3 seconds
2. Tap Login button → Login modal appears
3. Enter valid 10-digit mobile number → Number accepts proper formatting
4. Click "Get OTP" → OTP sent message appears
5. Enter valid OTP within 180 seconds → OTP accepts proper formatting
6. Submit OTP → User successfully logged in, redirected to homepage
7. Verify profile icon shows logged-in state → User avatar/initials visible

**Clean Up After**: Logout from the account

### TC_LOGIN_002
**Title**: Successful Social Media Login Integration
**Priority**: High
**Goal**: Verify users can login using Google account
**You Need First**:
- Mobile device
- Valid Google account
- Clear browser cache

**Test Steps**:
1. Open fabindia.com → Homepage loads
2. Tap Login button → Login modal appears
3. Select "Continue with Google" → Google login page opens
4. Select Google account → Permissions requested
5. Accept permissions → Redirects back to FabIndia
6. Verify account linked → Profile shows Google connection
7. Check saved addresses → Previous data preserved

**Clean Up After**: Unlink Google account, logout

### TC_LOGIN_003
**Title**: Failed OTP Verification Handling
**Priority**: High
**Goal**: Verify system properly handles invalid OTP attempts
**You Need First**:
- Android/iOS mobile device
- Valid Indian mobile number
- Clear browser cache

**Test Steps**:
1. Open fabindia.com → Homepage loads
2. Tap Login button → Login modal appears
3. Enter valid mobile number → Number accepts
4. Click "Get OTP" → OTP sent message appears
5. Enter incorrect 6-digit OTP → Error message shows "Invalid OTP"
6. Try 3 incorrect OTP attempts → Account temporarily locked message
7. Wait 5 minutes → Verify can request new OTP

**Clean Up After**: Clear browser cache

### TC_LOGIN_004
**Title**: Account Security - Password Change
**Priority**: Critical
**Goal**: Verify password change functionality with security checks
**You Need First**:
- Logged in account
- Valid mobile number for OTP
- Current password

**Test Steps**:
1. Go to Account Settings → Security section opens
2. Select Change Password → Password change form shows
3. Enter current password → Field validates
4. Enter new password meeting criteria → Strength indicator shows
5. Confirm new password → Matches validation
6. Submit change → OTP sent for verification
7. Enter correct OTP → Password successfully changed
8. Try old password → Login denied

**Clean Up After**: Reset to original password if needed

### TC_LOGIN_005
**Title**: Invalid Login Prevention
**Priority**: Critical
**Goal**: Verify account security measures for invalid login attempts
**You Need First**:
- Valid user account
- Invalid password combinations
- Clean browser session

**Test Steps**:
1. Go to login page → Login form displays
2. Enter valid mobile number → Number accepted
3. Enter invalid password 3 times → Warning message appears
4. Try 2 more invalid attempts → Account temporarily locked
5. Verify lock duration → 30 minutes countdown shown
6. Try valid password during lock → Access denied message
7. Check email/SMS → Account security alert received

**Clean Up After**: Wait for lock period to expire

## Product Search & Navigation (Positive & Negative Cases)

### TC_SEARCH_001
**Title**: Multilingual Voice Search
**Priority**: High
**Goal**: Verify voice search works with Hindi and English mixed queries
**You Need First**:
- Mobile device with microphone
- Quiet environment
- Chrome browser with Hindi language support

**Test Steps**:
1. Open homepage → Voice search icon visible
2. Tap voice search icon → Voice input modal opens
3. Speak "लाल साड़ी under २००० rupees" → Voice correctly interpreted
4. View search results → Red sarees under ₹2,000 displayed
5. Check filter tags → Price and color filters automatically applied
6. Verify product count → Shows relevant number of items

**Clean Up After**: Clear search history

### TC_SEARCH_002
**Title**: Regional Language Product Discovery
**Priority**: High
**Goal**: Verify search works with multiple Indian languages
**You Need First**:
- Mobile device
- Language input methods for Hindi, Tamil, Telugu
- Test product list in multiple languages

**Test Steps**:
1. Change interface to Hindi → UI elements update
2. Search "साड़ी" → Results show correctly
3. Switch to Tamil → Language changes
4. Search "பட்டு" (silk) → Relevant results appear
5. Use language mix "red साड़ी" → Shows correct results
6. Check product titles → Displayed in selected language
7. Verify prices and details → Correct in all languages

**Clean Up After**: Reset to English interface

### TC_SEARCH_003
**Title**: Search Error Handling
**Priority**: Medium
**Goal**: Verify graceful handling of invalid search inputs
**You Need First**:
- Mobile device
- List of test queries
- Clean search history

**Test Steps**:
1. Enter special characters "!@#$" → Error message shows
2. Search with excess length → Character limit enforced
3. Enter SQL injection test → Properly sanitized
4. Submit empty search → Appropriate message shown
5. Use all spaces "   " → Handles whitespace correctly
6. Try script tags → Properly escaped
7. Verify no system errors → User-friendly messages only

**Clean Up After**: Clear search history

### TC_SEARCH_004
**Title**: Product Filtering with Price Ranges
**Priority**: High
**Goal**: Verify filter combinations work correctly with Indian currency
**You Need First**:
- Mobile device
- Clean browser cache
- Category page loaded

**Test Steps**:
1. Navigate to "Women" → Category page loads
2. Apply price filter ₹1,000-₹3,000 → Products update
3. Add material filter "Cotton" → Products update with both filters
4. Sort by "Price: Low to High" → Products arranged correctly
5. Verify product prices → All within ₹1,000-₹3,000 range
6. Check product count matches filter summary → Numbers match

**Clean Up After**: Clear all filters

## Shopping Cart (Positive & Negative Cases)

### TC_CART_001
**Title**: Cart Updates During Festival Sale
**Priority**: Critical
**Goal**: Verify cart handles dynamic pricing during Diwali sale
**You Need First**:
- Logged in user account
- Active Diwali sale period
- Empty cart

**Test Steps**:
1. Add item with Diwali discount → Item added with sale price
2. Add item with BOGO offer → Both items show correct pricing
3. Apply Diwali coupon "DIWALI2025" → Additional discount applied
4. Update quantity of sale item → Price updates correctly
5. Verify total savings shown → Matches sum of all discounts
6. Check GST calculation → 18% on discounted price
7. Verify cart summary → All amounts in ₹ with proper formatting

**Clean Up After**: Empty cart, remove coupon

### TC_CART_002
**Title**: Cart Item Stock Validation
**Priority**: High
**Goal**: Verify real-time stock updates and inventory checks
**You Need First**:
- Products with limited stock
- Multiple devices/tabs
- Active user session

**Test Steps**:
1. Add item with 5 units left → Added to cart
2. Open same product in new tab → Stock shows 4 units
3. Try to add beyond stock → Error message appears
4. Add last items in stock → Success message
5. Check other users' cart impact → Stock properly managed
6. Verify cart timeout → Items released after 30 min
7. Check stock restored → Numbers updated correctly

**Clean Up After**: Remove items from cart

### TC_CART_003
**Title**: Failed Cart Operations
**Priority**: High
**Goal**: Verify system handles cart operation failures gracefully
**You Need First**:
- Unstable network connection
- Multiple items in cart
- Mix of in-stock and out-of-stock items

**Test Steps**:
1. Add items during poor connection → Retry mechanism works
2. Update quantities offline → Changes queue for sync
3. Remove item without connection → Proper error shown
4. Add out-of-stock item → Clear notification shown
5. Apply expired coupon → Valid error message
6. Add item exceeding limit → Max quantity enforced
7. Check cart consistency → Data integrity maintained

**Clean Up After**: Clear cart, restore connection

## Payment & Checkout (Positive & Negative Cases)

### TC_PAY_001
**Title**: UPI Payment Flow
**Priority**: Critical
**Goal**: Verify complete UPI payment flow with Indian payment gateway
**You Need First**:
- Logged in account
- Cart with items worth ₹2,000+
- Valid UPI ID
- Test payment gateway credentials

**Test Steps**:
1. Proceed to checkout → Address page loads
2. Select/enter delivery address → Valid Indian pin code accepted
3. Choose UPI payment → UPI options displayed
4. Enter UPI ID → Format validation works
5. Click "Pay Now" → Payment gateway loads
6. Approve payment in UPI app → Success callback received
7. Verify order confirmation → Order ID and GST invoice generated

**Clean Up After**: Note order ID for future reference

### TC_PAY_002
**Title**: Successful Cash on Delivery
**Priority**: High
**Goal**: Verify COD payment option works for eligible locations
**You Need First**:
- Delivery address in COD serviceable area
- Order within COD limit
- Valid mobile for OTP

**Test Steps**:
1. Select COD payment option → Availability checked
2. Verify order value limits → Within COD range
3. Confirm mobile number → OTP sent
4. Enter valid OTP → Order confirmed
5. Check order status → Marked as COD
6. Verify SMS confirmation → Contains order details
7. Check delivery instructions → COD amount mentioned

**Clean Up After**: Cancel order if needed

### TC_PAY_003
**Title**: Payment Gateway Timeout
**Priority**: Critical
**Goal**: Verify system handles payment gateway timeouts
**You Need First**:
- Test payment gateway
- Slow network simulation
- Active cart with items

**Test Steps**:
1. Start payment process → Gateway loads
2. Simulate timeout → Loading indicator shows
3. Check order status → Marked as pending
4. Verify payment retry → Option available
5. Check cart status → Items still reserved
6. Monitor timeout period → 15-minute limit
7. Verify order cancellation → Auto-cancel after timeout

**Clean Up After**: Clear pending transactions

### TC_PAY_004
**Title**: EMI Option Verification
**Priority**: High
**Goal**: Verify EMI options for major Indian banks
**You Need First**:
- Cart value above ₹3,000
- Test credit card details
- List of supported banks

**Test Steps**:
1. Proceed to checkout → Payment page loads
2. Select EMI option → Bank options displayed
3. Choose HDFC Bank → EMI plans shown
4. Verify 3/6/9/12 month options → Correct interest rates displayed
5. Select 3-month plan → EMI calculation shown
6. Check processing fee → Fee added to first EMI
7. Verify total payment → Matches EMI * months + fees

**Clean Up After**: Cancel EMI selection

## Mobile Experience (Positive & Negative Cases)

### TC_MOB_001
**Title**: Mobile App-like Features on Browser
**Priority**: Critical
**Goal**: Verify PWA features work on mobile browser
**You Need First**:
- Mobile device with Chrome
- 4G connection
- Location services enabled

**Test Steps**:
1. Open fabindia.com → Install PWA prompt appears
2. Add to home screen → Icon added correctly
3. Launch from icon → App-like experience opens
4. Test offline mode → Basic browsing works
5. Check push notifications → Permission prompt appears
6. Enable notifications → Order updates received
7. Verify app performance → No lag in transitions

**Clean Up After**: Clear site data, remove from home screen

### TC_MOB_002
**Title**: Mobile Image Optimization
**Priority**: High
**Goal**: Verify images load optimally on different network speeds
**You Need First**:
- Various mobile devices
- Network throttling tools
- Different screen resolutions

**Test Steps**:
1. Load product images on 4G → Images load quickly
2. Switch to 3G → Progressive loading works
3. Check image quality → Appropriate for screen
4. Verify lazy loading → Works while scrolling
5. Test zoom functionality → High-res version loads
6. Check thumbnail loading → Quick preview available
7. Verify offline cache → Previously viewed images available

**Clean Up After**: Clear image cache

### TC_MOB_003
**Title**: Mobile Network Resilience
**Priority**: Critical
**Goal**: Verify app behavior during poor network conditions
**You Need First**:
- Network throttling tool
- Active user session
- Partial cart contents

**Test Steps**:
1. Browse with unstable network → Graceful degradation
2. Add to cart offline → Queue for sync
3. Check offline content → Available and current
4. Restore connection → Data syncs correctly
5. Verify error messages → User-friendly format
6. Check recovery actions → Clear next steps shown
7. Test background sync → Works when online

**Clean Up After**: Reset network settings

## Order Management (Positive & Negative Cases)

### TC_ORD_001
**Title**: GST Invoice Download
**Priority**: High
**Goal**: Verify GST invoice generation and download
**You Need First**:
- Completed order
- Logged in account
- Order with multiple items

**Test Steps**:
1. Go to Order History → Orders listed
2. Select recent order → Details displayed
3. Click "Download Invoice" → GST invoice generates
4. Verify invoice format → Contains GSTIN, HSN codes
5. Check item-wise GST → Tax calculated per category
6. Verify business details → FabIndia GSTIN correct
7. Validate total amount → Base + GST matches order total

**Clean Up After**: Delete downloaded invoice

### TC_ORD_002
**Title**: Order Tracking for Multiple Addresses
**Priority**: High
**Goal**: Verify order tracking for split delivery
**You Need First**:
- Order with multiple items
- Different delivery addresses
- Active shipments

**Test Steps**:
1. Go to Order Tracking → Tracking page loads
2. View split order status → Individual tracking IDs shown
3. Check delivery partners → Correct for each region
4. Verify estimated dates → Based on pin code zones
5. Track each shipment → Status updates available
6. Check SMS updates → Triggered for each movement
7. Verify address display → Properly formatted Indian addresses

**Clean Up After**: Clear tracking history

### TC_ORD_003
**Title**: Order Cancellation Flow
**Priority**: High
**Goal**: Verify order cancellation process and refund initiation
**You Need First**:
- Recent order within cancellation window
- Order with online payment
- Valid reason for cancellation

**Test Steps**:
1. Go to Order Details → Cancellation option available
2. Select cancel order → Reason list displays
3. Choose valid reason → Confirmation prompt shows
4. Confirm cancellation → Order status updates
5. Check refund status → Initiated automatically
6. Verify refund amount → Includes all applicable taxes
7. Check notification → Cancellation confirmed via SMS/email

**Clean Up After**: Archive cancelled order

### TC_ORD_004
**Title**: Failed Delivery Handling
**Priority**: High
**Goal**: Verify system handles failed delivery attempts
**You Need First**:
- Active order in transit
- Delivery attempt scenario
- Customer unavailable situation

**Test Steps**:
1. Simulate failed delivery → Status updates
2. Check customer notification → SMS/email sent
3. Verify reattempt schedule → Next attempt date shown
4. Check delivery instructions → Updates allowed
5. Monitor status changes → Timeline accurate
6. Verify contact options → Support details available
7. Test rescheduling → New slot selection works

**Clean Up After**: Reset delivery preferences

## Edge Cases & Error Handling (Positive & Negative Cases)

### TC_ERR_001
**Title**: Network Issues During Payment
**Priority**: Critical
**Goal**: Verify payment recovery during poor network
**You Need First**:
- Cart with items
- Network throttling tool
- Payment method ready

**Test Steps**:
1. Start checkout → Payment page loads
2. Enable network throttling → Simulate poor connection
3. Initiate payment → Process starts
4. Interrupt connection → Connection lost message
5. Restore connection → Recovery options shown
6. Check order status → Pending payment status
7. Retry payment → Successfully completes

**Clean Up After**: Disable network throttling, clear cart

### TC_ERR_002
**Title**: Session Management
**Priority**: High
**Goal**: Verify cart persistence across sessions
**You Need First**:
- Logged in user
- Items in cart
- Multiple devices

**Test Steps**:
1. Add items to cart on mobile → Cart updates
2. Log in on desktop → Cart syncs
3. Update quantities on desktop → Changes reflect
4. Close mobile browser → Session ends
5. Reopen mobile site → Cart restored
6. Check prices and items → All data consistent
7. Verify cart total → Matches across devices

**Clean Up After**: Clear cart, logout from all devices
