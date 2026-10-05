# JazzCash onboarding guide (before you integrate)

> Reference only. This summarises what the JazzCash Sandbox Portal asks for during onboarding so you know what to prepare. The portal is the source of truth and its fields can change. This project is not affiliated with JazzCash.

Onboarding is **mandatory** before your business can use JazzCash in your payment flow. The portal's left menu has **Onboarding**, **Documentation** and **Integration**. Integration (where your Merchant ID, Password, Integrity Salt, Return URL and IPN URL live) stays greyed out until your profile is approved.

Create your sandbox account at <https://onlinepayments.jazzcash.com.pk/sandbox-frontend/>, then complete the three steps in order. After sign-up, send your Merchant ID to JazzCash so their team can enable the payment methods you need.

## Step 1: Basic Information
Answer every required question. Some questions change with your business type.

| Field | Notes |
|---|---|
| Merchant Type | Government, Private Limited Company, Partnership, Sole Proprietor |
| Merchant Product Solution Type | Gateway, Collection, Disbursement, All Solutions |
| Name, Website | Your business name and public site |
| Category | Pick the closest business category (a searchable list) |
| Country, Province, City | Country list currently offers Pakistan. Province and City are filled from your choice (for example Capital → Islamabad) |
| Full Address | Business address |
| Personal Information of Signatory | Full name, email, CNIC, resident address, mobile number. Use the **+** button to add more signatories |
| Product Selection | Toggles for **Gateway Collection** and **Disbursement** |
| NTN | National Tax Number |

**Contacts:** use **Add Contact** to define the people JazzCash will reach. You need **at least one business and one technical contact, or one contact of type "Both"**, and **at least one default contact**. Each contact has full name, email, phone number, contact type (Business, Technical or Both) and an "Is Default" switch.

Press **Apply** to submit. You can go back and edit this step from the title bar while you are still on the document step.

## Step 2: Upload Documents
Required documents depend on your merchant type. Typical list for a Private Limited Company:

| Document | Required | Template |
|---|---|---|
| NTN Number | Yes | Download Template available |
| Account opening request | Yes | Download Template available |
| List Directors on Letterhead | Yes | - |
| Article of Association | Yes | - |
| Memorandum of Association | Yes | - |
| Biometrics (back office will add) | Optional | - |

- Maximum file size is **5 MB** per file. Drag a file in or click to pick one.
- Uploaded files can be previewed, downloaded, replaced or removed (the eye, file and cross icons beside each item) until you apply.
- Some business types need no documents at all. You then only accept the agreement.
- At the bottom, open and read the **Terms and Conditions** (payment acceptance services with Mobilink Microfinance Bank Limited), press **Accept**, tick **"I accept the terms and conditions"**, then press **Apply**.

## Step 3: Verification
Nothing to do. JazzCash reviews your information and documents and emails you the result. The page shows **"Awaiting manager approval"** until then. You cannot edit earlier steps while verification is pending, unless your application is rejected or JazzCash asks for updates.

## After approval
1. Open **Integration → Credentials** and copy your **Merchant ID**, **Password** and **Integrity Salt**. Save your **Return URL** (and **IPN URL** if you use IPN). The Return URL must match what you send in requests exactly.
2. Ask JazzCash to enable the payment methods you need (mobile account, voucher, card, Apple Pay, Google Pay).
3. Run `npx @icodedigita/jazzcash-setup` and paste the credentials into the wizard, or set them in `.env`.
4. Complete the sandbox test transactions JazzCash asks for (mobile account, voucher, credit/debit) and send the screenshots as they instruct.
5. Request live credentials and switch `JAZZCASH_MODE=live`.
6. The portal also offers a Hash Calculator, REST API / Checkout Page / Account Linking simulators, and test card and mobile-account data. This project's wizard includes its own offline versions of these.

## Checklist
- [ ] Business type and solution type chosen
- [ ] NTN, signatory CNIC and address ready
- [ ] At least one business and one technical contact (or "Both"), one marked default
- [ ] Documents scanned, each under 5 MB
- [ ] Terms accepted and application submitted
- [ ] Approval email received
- [ ] Credentials and Return/IPN URLs saved
