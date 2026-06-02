# Test Case Standard

Test cases are written so that **anyone in the company** can run them, not just the author. Every test case must follow this standard before it leaves **In Progress**.

## 1. Summary (Title)

Format: `{Main Feature} | {Summary of what is being tested}`

- Use a pipe separator followed by a very clear summary of what is being tested.
- Example: `Order History | Guest user cannot access order history`

## 2. Description

One sentence explaining what the test validates and why it matters.

Format: *"Validates that [behavior] so that [business reason / ticket reference]."*

Example: *"Validates that an unauthenticated user is blocked from the order history page so that access is prevented."*

## 3. Test Case Reporting Fields: All Required

> Every test case must have **all** of these fields filled out before it leaves In Progress.

| Field | Notes |
|-------|-------|
| **Priority** | Determines if the test runs during regression. *Medium-priority regression tests are frequently left out, if a test is really worth running each cycle, set it High or Critical.* |
| **Automation Status** | Tracks automation coverage across the suite. |
| **Test Kind** | Regression or Feature, drives which cycle this test runs in. |
| **Components** | Links the test to the correct product area for filtering and reporting. |
| **Needs Updating** | Flags stale tests so they can be identified and cleaned up. |
| **Manual Time Estimate** | Required for automation ROI and regression-cycle planning. |
| **Product(s)** | Select the product(s) used (can be multiple). Use *Not Applicable* if no product is involved. If the product isn't an option, ask the QA Manager to add it. |
| **Tax Setting** | Select the relevant tax setting. Use *Not Applicable* if taxes aren't involved. |

## 4. Preconditions

Preconditions establish the state the system must be in before the test begins.

- **Quick config change** (e.g. toggle a setting to false): add it as the **first step**: detail exactly *how* to make the change.
- **Larger setup** (e.g. a data state): create a precondition ticket, link it in the Preconditions field, and call it out explicitly in the first step so it's visible.

## 5. Writing Steps

### First step rules
The first step must establish test context. Address each of these in order (skip any that don't apply):

1. **Precondition reference**: if one exists
2. **Login state** (logged in or logged out), if it matters
3. **Specific user required**: if a particular account is needed

### Action rules
- When a step involves multiple actions, use a **bulleted list inside the step**: don't chain actions into multiple sentences.
- If a specific product is needed, include the full breadcrumbs: `Category > Subcategory > Product Name`, and select it in the **Product(s)** field. (In Commerce, add *"This is a QA Product, Do Not Modify"* to the product description.)
- Be as specific as possible: exactly what must be done to reach the expected result (e.g. which attribute values to select).
- Use the word **"click"** for button interactions, and always use the **exact button label**.

### Data rules
- Include the **end URL** (everything after `.net`) when a specific product page is required.
  e.g. `/l/purchase-team-products/attribution-differences/p/assignment-on-pdp-happy-path`

### Expected result rules
- Expected results must be **unambiguous**, with no room for interpretation.
- Use **definitive language**: *"user is redirected to…"*, *"error message displays…"*.
- **Never use "should" or "could"**: they leave room for interpretation.
- If pricing matters, **specify the exact price**.
- Where it makes sense, include a **negative path inline**: test the failure state *before* the happy path. (e.g. during account creation, check that a DOB below the minimum age shows an error; once corrected, the account is created.)

### Checkout flow rules
- If the test is **focused on checkout**: detail every step of the checkout flow.
- If checkout is a **means to an end**: every step does not need to be explicit.
- Every **"Successful Checkout"** expected result must cover all of:
  1. Order confirmation is successful
  2. Admin > Aspenware Commerce > Order Queue, status = success
  3. Email confirmation received
  4. RTP > Customer > Order History > Transaction Viewer, (when it makes sense) expected header codes, assignee, dates, price
  5. RTP > Customer > Transaction History, (when it makes sense) what's expected to be seen
  6. Payment Gateway Dashboard, (when it makes sense) what's expected to be seen

## 6. Postconditions

Written as the **last step**. Covers any teardown or state reset needed after the test completes.

## 7. Process

| Stage | Who | Notes |
|-------|-----|-------|
| **Create** | Author | Created before the dev ticket leaves In Progress |
| **Initial Run** | Author | Author runs it first and updates the test case based on findings |
| **Feature Review** | Product | Product reviews test cases as part of acceptance |
| **Regression Review** | A different QA Engineer | Cross-trains on the feature; reviews for comprehension. Set Test Kind = Regression before this stage |
| **Updating** | Author or running QA | Update when the feature changes, prefer a tracked ticket. If found during regression with no ticket, check with QA + Product Lead before updating |

## Open items

- Align as a team on the QA Jira workflow: **Backlog → In Progress → Review → Done/Active**
