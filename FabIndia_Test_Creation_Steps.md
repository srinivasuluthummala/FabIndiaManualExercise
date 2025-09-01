# 5 Steps to Create Detailed Manual Test Cases for FabIndia.com

## Step 1: Set Context with a Simple Prompt

Start by creating a clear context for your test case development:

"You are a QA Engineer creating test cases for fabindia.com, India's largest online shopping website serving 100+ million Indian customers. Focus on mobile-first testing, UPI payments, and festival shopping patterns. Key priorities are preventing payment failures, ensuring accurate GST calculations, and optimizing mobile experience since most customers shop on phones."

## Step 2: Use the Standardized Template

Every test case must follow this exact format:

```
**Test ID**: TC_[Area]_[Number] (e.g., TC_SEARCH_001)
**Title**: What you're testing in plain English
**Priority**: Critical/High/Medium/Low
**Goal**: One sentence explaining what this test proves
**You Need First**: 
- Browser and device setup
- Account type needed
- Starting conditions
**Test Steps**:
1. Action → Expected Result
2. Next Action → Expected Result
[Continue for each step]
**Clean Up After**: Reset steps for next test
```

## Step 3: Follow the Perfect Example

Reference this example for structure and detail level:

```
**Test ID**: TC_SEARCH_002
**Title**: Search for products using Hindi keywords shows relevant results
**Priority**: High
**Goal**: Verify Indian customers can find products using their preferred language

**You Need First**:
- Chrome browser with Hindi keyboard enabled
- Clear fabindia.com homepage
- Test from Indian location

**Test Steps**:
1. Type "मोबाइल" in search box → Hindi text appears correctly
2. Press Enter → Results page loads within 3 seconds
3. Check first 10 results → All show mobile phones or accessories
4. Verify result count → Shows "1-48 of over 1,000 results for मोबाइल"
5. Apply price filter ₹10,000-₹20,000 → Results update to show only phones in that range

**Clean Up After**: Clear search history
```

## Step 4: Include Indian Market Requirements

For each test case, incorporate these key aspects:

### Money and Regulations
- Verify prices in Indian rupees (₹) with proper formatting
- Validate GST calculations visibility and accuracy
- Test cash on delivery for tier-2/3 cities
- Verify EMI options with major Indian banks

### Cultural Considerations
- Include festival season high-traffic scenarios
- Test regional language support
- Account for shared family accounts
- Ensure mobile-first functionality

### Quality Requirements
- Define specific pass/fail criteria
- Account for varied internet speeds
- Include thorough cleanup steps
- Use realistic Indian test data

### Priority Guidelines
- Critical: Payment, search, mobile experience
- High: Product info, cart management
- Medium: Recommendations, reviews
- Low: Social features, personalization

## Step 5: Apply Best Practices

When writing each test case:

1. Use clear, consistent language
2. Keep tests atomic (one objective per test)
3. Ensure repeatability and independence
4. Write from real user perspective
5. Include both positive and negative scenarios
6. Use consistent identifiers
7. Keep test data realistic
8. Include specific validation criteria

Remember to test these key areas with both happy path and error scenarios:
- User Login (mobile/OTP)
- Product Search (multilingual)
- Shopping Cart
- Payment (UPI/banking)
- Checkout (Indian addresses)
- Orders (GST/tracking)

For each area, create:
- 3-4 positive test cases
- 2-3 negative test cases
- 1-2 edge case scenarios
