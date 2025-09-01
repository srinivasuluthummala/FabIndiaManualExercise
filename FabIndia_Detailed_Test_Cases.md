# FabIndia E-Commerce Test Cases Documentation

## Test Case Documentation Format

Each test case follows this standardized format:

1. **Test Case ID**: Unique identifier prefixed with module name
2. **Title**: Brief description of what is being tested
3. **Module**: Functional area of the application under test
4. **Priority**: Business impact (Low/Medium/High/Critical)
5. **Preconditions**: Required setup or system state
6. **Test Data**: Specific inputs and values needed
7. **Test Steps**: Sequential actions with expected results
8. **Expected Result**: Correct system behavior
9. **Actual Result**: Observed behavior during execution
10. **Status**: Pass/Fail/Blocked/Not Executed
11. **Notes/Comments**: Additional information or observations

## User Authentication Module

### TC_LOGIN_001
**Test Case ID**: TC_LOGIN_001
**Title**: Mobile Number OTP Login - Happy Path
**Module**: User Authentication
**Priority**: Critical

**Preconditions**:
- Android/iOS mobile device with Chrome browser
- Active internet connection
- No active user session
- Clean browser cache and cookies

**Test Data**:
- Valid 10-digit Indian mobile number: 9999999999
- Valid OTP (will be received during test)
- Test user credentials in QA environment

**Test Steps and Expected Results**:
1. Open fabindia.com on mobile browser
   - Homepage loads within 3 seconds
   - All elements are properly rendered
   - Mobile-optimized layout displayed

2. Tap Login button
   - Login modal appears smoothly
   - Modal is centered on screen
   - All input fields are visible
   - Close button is present

3. Enter valid 10-digit mobile number
   - Number field accepts only numeric input
   - Auto-formatting applies (XXX-XXX-XXXX)
   - Field validates Indian mobile format
   - Error messages show for invalid formats

4. Click "Get OTP"
   - Button becomes disabled after click
   - Loading indicator appears
   - Success message shows "OTP sent to XXXXXX9999"
   - 180-second countdown timer starts

5. Enter valid OTP within 180 seconds
   - Each digit appears as dot/asterisk
   - Field accepts only numeric input
   - Auto-focus moves between digit boxes
   - Backspace clears previous digit

6. Submit OTP
   - Loading indicator appears
   - Success message shows on valid OTP
   - Error message appears for invalid OTP
   - Retry option available for failures

7. Verify profile icon shows logged-in state
   - User redirected to homepage
   - Profile icon shows user initials/avatar
   - Welcome message displays user name
   - Previous session data restored

**Actual Result**: [To be filled during execution]

**Status**: Not Executed

**Notes/Comments**:
- OTP validity period is 180 seconds
- Test on both Android and iOS devices
- Verify SMS delivery on registered mobile number
- Check for proper error messages if wrong OTP entered

**Clean Up Steps**: 
- Logout from the account
- Clear browser cache and cookies

## Product Search Module

### TC_SEARCH_001
**Test Case ID**: TC_SEARCH_001
**Title**: Multilingual Voice Search Functionality
**Module**: Product Search
**Priority**: High

**Preconditions**:
- Mobile device with working microphone
- Chrome browser with Hindi language support
- Quiet testing environment
- Clear search history
- Stable internet connection

**Test Data**:
- Hindi voice input: "लाल साड़ी"
- Price range: ₹2000
- Expected result count: > 0
- Test product categories: Women's Wear

**Test Steps and Expected Results**:
1. Access FabIndia homepage
   - Page loads within 3 seconds
   - Search bar visible in header
   - Voice search icon clearly visible
   - Search bar shows placeholder in Hindi/English

2. Activate voice search
   - Microphone permission prompt appears (if first time)
   - Voice input modal opens with animation
   - Visual feedback shows listening state
   - "Speak now" prompt in Hindi/English

3. Speak search phrase in Hindi "लाल साड़ी"
   - Voice input indicator responds to speech
   - Real-time voice-to-text shown
   - Correct Hindi text displayed
   - Auto-submits after speech completion

4. Review search results
   - Results load within 2 seconds
   - Products match search criteria
   - Hindi search term shown in results header
   - Relevant categories highlighted
   - Product images load progressively

5. Apply price filter "Under ₹2000"
   - Price range selector responds instantly
   - Results refresh automatically
   - Loading indicator shows during update
   - URL updates with filter parameters
   - Products within price range displayed

6. Verify filter tags
   - Applied filters shown as removable tags
   - Both language and price filters visible
   - Clear all filters option available
   - Tags show correct Hindi text
   - Price range shown in Indian format

7. Check result count
   - Total count matches visible results
   - "Showing X of Y results" in both languages
   - Count updates with filter changes
   - Pagination/infinite scroll working
   - "No results" message in Hindi if applicable

**Actual Result**: [To be filled during execution]

**Status**: Not Executed

**Notes/Comments**:
- Test in different ambient noise conditions
- Verify accuracy of voice recognition
- Check performance with mixed language inputs
- Validate search result relevance

**Clean Up Steps**:
- Clear search history
- Reset language preferences

## Payment Module

### TC_PAY_001
**Test Case ID**: TC_PAY_001
**Title**: UPI Payment Flow Validation
**Module**: Payment & Checkout
**Priority**: Critical

**Preconditions**:
- Logged in user account
- Active cart with items worth ₹2,000+
- Valid UPI ID registered with bank
- Test payment gateway credentials
- UPI app installed on device
- Stable internet connection

**Test Data**:
- Test UPI ID: test.user@upi
- Order items: 3 different products
- Cart value: ₹2,500
- Delivery address with PIN: 560001
- Test payment gateway endpoint
- GST calculation reference data

**Test Steps and Expected Results**:
1. Proceed to checkout
   - Cart summary shows correctly
   - All items listed with quantities
   - Subtotal calculated accurately
   - Delivery fee estimation shown
   - GST breakup displayed by category
   - Total amount in ₹ with proper formatting

2. Select/enter delivery address
   - Address form loads with all fields
   - PIN code validation works instantly
   - City/State auto-populates based on PIN
   - Delivery timing estimate updates
   - Serviceability check performed
   - Address saved to account if selected

3. Choose UPI payment method
   - All payment options displayed
   - UPI section expands smoothly
   - Popular UPI apps shown as icons
   - QR code option available
   - Security badges displayed
   - Payment gateway fees (if any) shown

4. Enter UPI ID
   - Format validation (username@upi)
   - Real-time validation feedback
   - Recent UPI IDs shown (if any)
   - Clear button available
   - Error messages in proper language
   - Save UPI ID option available

5. Click "Pay Now"
   - Final amount verification shown
   - Payment summary displayed
   - Secure gateway page loads
   - Loading indicator appears
   - Session timeout counter visible
   - Cancel transaction option available

6. Complete UPI app authorization
   - Deep link to UPI app works
   - Correct amount shown in UPI app
   - Merchant details accurate
   - Transaction reference visible
   - Success/failure callback received
   - Returns to merchant site properly

7. Verify order confirmation
   - Success page loads immediately
   - Order ID displayed prominently
   - Order summary shown correctly
   - Delivery estimate provided
   - Track order button available
   - Email/SMS confirmation sent

8. Check GST invoice generation
   - Invoice downloads as PDF
   - All GST details present (GSTIN, HSN)
   - Item-wise tax breakup shown
   - Calculations are accurate
   - Digital signature present
   - Invoice number generated properly

**Actual Result**: [To be filled during execution]

**Status**: Not Executed

**Notes/Comments**:
- Test with multiple UPI apps (BHIM, PhonePe, GPay)
- Verify timeout handling
- Check payment failure scenarios
- Validate GST calculations
- Verify digital signature on invoice
- Test network interruption scenarios

**Clean Up Steps**:
- Note order ID for reference
- Archive test transaction details
- Clear payment gateway test logs

## Mobile Experience Module

### TC_MOB_001
**Test Case ID**: TC_MOB_001
**Title**: Progressive Web App Installation and Offline Functionality
**Module**: Mobile Experience
**Priority**: High

**Preconditions**:
- Mobile device with Chrome browser
- Clean browser cache
- No existing PWA installation
- Variable network conditions setup
- Location services enabled

**Test Data**:
- Test products for offline access
- Network throttling profiles
- Cache storage limits
- Push notification templates

**Test Steps**:
1. Visit fabindia.com on mobile
2. Trigger PWA installation prompt
3. Complete PWA installation
4. Test offline access
5. Enable push notifications
6. Verify app-like navigation
7. Test background sync
8. Check performance metrics

**Expected Result**:
- PWA install prompt appears
- Installation completes successfully
- Offline content accessible
- Push notifications working
- Smooth app-like transitions
- Background sync functional
- Performance meets PWA metrics

**Actual Result**: [To be filled during execution]

**Status**: Not Executed

**Notes/Comments**:
- Check Lighthouse PWA scores
- Verify offline catalog browsing
- Test push notification delivery
- Monitor storage usage
- Validate service worker updates

**Clean Up Steps**:
- Uninstall PWA
- Clear site data
- Reset notification permissions

## Cart Management Module

### TC_CART_001
**Test Case ID**: TC_CART_001
**Title**: Festival Sale Cart Management
**Module**: Shopping Cart
**Priority**: Critical

**Preconditions**:
- Active Diwali sale period
- User logged in
- Empty cart
- Sale prices activated
- Multiple promo codes available

**Test Data**:
- Test products with discounts
- Diwali coupon code: DIWALI2025
- BOGO offers
- Cart value thresholds
- GST rates for different categories

**Test Steps**:
1. Add sale items to cart
2. Add BOGO offer items
3. Apply festival coupon
4. Update item quantities
5. Verify discount calculations
6. Check GST computation
7. Validate cart summary

**Expected Result**:
- Sale prices correctly applied
- BOGO offers properly calculated
- Coupon discount added
- Quantity updates reflect immediately
- GST calculated correctly
- Total savings displayed accurately
- Cart persists across sessions

**Actual Result**: [To be filled during execution]

**Status**: Not Executed

**Notes/Comments**:
- Verify time-sensitive offers
- Check multiple discount stacking
- Test cart sync across devices
- Validate price change notifications
- Check inventory holds

**Clean Up Steps**:
- Empty cart
- Remove applied coupons
- Clear local storage
