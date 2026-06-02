# Example Tickets

Four real tickets, shown here to work or paste from. **Product:** if you didn't bring a feature, the rough ones (**CHK-3334**, **PUR-6336**) are raw material to **explore, split, and turn into a ticket tree**: the kind of vague work OpenSpec is built for. (Don't have a feature big enough to split? Treat the whole **guest-checkout** example in [The OpenSpec Process](openspec-process.md) as your feature.) **QA:** **PUR-6243** and **QUAL-4510** are the format to copy. The two clean examples (**PUR-6243**, **PPA-4978**) also show what "clear, testable behavior" looks like.

| Ticket | Type | Use it as | Why |
|--------|------|-----------|-----|
| **PUR-6243** | Bug / Purchase | ✅ **Good example to copy** | Clean Given/When/Then AC + a test-case-to-AC-to-evidence table. The gold standard for shape. |
| **PPA-4978** | Bug / PPA | ✅ **Good QA example** | Business-rule AC + a scenario/evidence table; AC even bakes in "create an AQA test." |
| **CHK-3334** | Story / Checkout | ✏️ **Sharpen this (Product)** | AC written as nested numbered requirements, real, but not testable as written. |
| **PUR-6336** | Task / AI data | ✏️ **"Is this even AC?" (Product/QA)** | An implementation checklist masquerading as acceptance criteria. Great for "what's wrong with this?" |

> **QA format:** your team's **[Test Case Standard](https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard)** is in Confluence; the complete **`QUAL-4510`** example comes from the session materials. Use those as the format. Other QUAL IDs referenced in these tickets (QUAL-5013, QUAL-2591) are still placeholders we don't have bodies for.

---

## ✅ PUR-6243: the shape to copy (Given / When / Then)

> **AC 1, Non-fenced Cloud PDP or PCP page + valid discount voucher code**
> - GIVEN a user navigates to a non-fenced Cloud PDP or PCP URL with a valid discount voucher code appended
> - WHEN the success modal appears and the user dismisses it (via X or clicking outside)
> - THEN the Cloud PDP or PCP page loads successfully with no interruption or stall
>
> **AC 2, Non-fenced Cloud PDP or PCP page + invalid voucher code**
> - GIVEN a user navigates to a non-fenced Cloud PDP or PCP URL with an invalid voucher code appended
> - WHEN the error modal appears and the user dismisses it (via X, Cancel, or clicking outside)
> - THEN the page loads successfully, the "Page not found" page must NOT load

It also maps each AC to a test case and to video evidence. **That mapping is the bit to copy in the QA room.**

## ✅ PPA-4978: business-rule AC with testability baked in

> 1. Move the customer-contact update to **after** the auth call.
> 2. **Create a new AQA test case** to ensure this bug does not return.
> 3. Nop contact/customer tables are not updated until the RTP auth-profile update succeeds.
> 4. RTP email profile is only updated if the auth-profile update succeeds.
> 5. When an email already in use is submitted, the "already in use" error shows, and **no** profile/table updates happen.

Plus a Problem Statement, Impact Statement, Steps to Reproduce, and a scenario table with PASS evidence. **Good model for QA test-case structure.**

---

## ✏️ CHK-3334: sharpen this (Product)

The AC, as written (real):

> 1. Within the Billing Address form for ALL payment gateways, a new checkbox is introduced, "Save this as my primary address", selected by default, always displayed.
> 2. When selected, the billing address is saved to the AW DB **and** sent to RTP as primary.
> 3. When not selected, saved to the AW DB only; nothing sent to RTP.
> 4. Regression: Order Details must reflect whatever was entered at checkout.

**Why it's a good practice target:** it's requirement-shaped, not behavior-shaped. "Always displayed", under every state? Phone required only for FP 3DS, where's that scenario? **Explore** it with Claude and the gaps fall out; **spec** it as testable scenarios and they get answered. (The ticket's own "Testing Notes" scenario table is a hint at what the spec should cover.)

## ✏️ PUR-6336: is this even AC?

Its "Acceptance Criteria" is a nested implementation checklist, "add a section to the flat file," "identify what tool calls we need," "generate option-2 and option-3 flat files for these 30 product IDs." **That's a task breakdown, not acceptance criteria.** Use it to ask: *what would "done and correct" actually look like to someone verifying this?*, and rewrite it as outcomes.

---

## How to paste these in

**Product (explore → split → tickets):**
> *"Let's use OpenSpec. Explore this whole feature with me before we write or split anything, [paste CHK-3334, or your own]. What are all the distinct behaviors here? What would a developer still have to guess? Ask me one thing at a time."*

then `grill me` to find the gaps, then:
> *"Split this into independently shippable behaviors (one bucket each, named like a behavior, with a one-line 'Why'). Then create the OpenSpec change, a proposal plus a spec per behavior, and from it an Epic + a Story per behavior + sub-tasks in my own Jira project. Show me the tree before creating anything."*

**QA:**
> *"Follow our Test Case Standard at https://aspenware.atlassian.net/wiki/spaces/QA/pages/4137582614/Test+Case+Standard and match the format of the `QUAL-4510` example. Draft test cases for this story: Action / Data / Expected Result, definitive language, negative path inline. If test cases already exist, normalize them to the standard and flag duplicates instead."*
