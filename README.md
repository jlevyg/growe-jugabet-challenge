# Test plan

- [Test plan](#test-plan)
    - [1. Introduction](#1-introduction)
        - [1.1 Objective](#11-objective)
        - [1.2 Scope of Testing](#12-scope-of-testing)
        - [1.3 Testing Approach](#13-testing-approach)
        - [1.4 Environments](#14-environments)
    - [2. Test Cases](#2-test-cases)
    - [3. Bugs Report](#3-bugs-report)
    - [4. Feedback/Recommendations](#4-feedback/recommendations)




## 1. Introduction

### 1.1 Objective

To verify that users can seamlessly navigate from the landing page to the registration form and complete the registration process without encountering any issues.

### 1.2 Scope of Testing

	•	Navigation from the landing page to the registration form.
	•	Functionality and usability of the registration form.
	•	Validation of input fields and error handling.
	•	Cross-browser and cross-device compatibility.

### 1.3 Testing Approach

	•	Functional Testing: Verify that all elements and interactions on the page work as intended.
	•	Usability Testing: Evaluate the intuitiveness of the flow for a first-time user.
	•	Cross-Browser Testing: Check compatibility on popular browsers (e.g., Chrome, Firefox, Safari).
	•	Responsive Testing: Test on desktop and mobile devices.
	•	Negative Testing: Enter invalid data to verify error handling.
 
### 1.4 Environments

	•	Browsers: Chrome (latest), Firefox (latest), Safari.
	•	Devices: Desktop, Mobile (iOS).

 ### 2 Test Cases

| Test Case | Steps | Expected Result |
|-----------|--------|-----------------|
| Navigation from Landing Page to Registration Form | 1. Open the landing page: https://win.jugabet.cl/casino/wheel-v2/<br>2. Click on the "Únete" button | User is redirected to the registration form page |
| Registration with Valid Data | 1. Navigate to the registration form<br>2. Fill in all required fields with valid data<br>3. Click on "Registrarse" button to submit the form | User account is successfully created, and a confirmation message is displayed |
| Registration with Invalid Email Format | 1. Navigate to the registration form<br>2. Enter an invalid email address<br>3. Fill in other fields with valid data<br>4. Submit the form | • An error message is displayed indicating an invalid email format<br>• "Registrarse" button is disabled |
| Registration with Weak Password | 1. Navigate to the registration form<br>2. Enter a password that doesn't meet the required criteria<br>3. Fill in other fields with valid data<br>4. Submit the form | • An error message is displayed indicating that the password is too weak<br>• "Registrarse" button is disabled<br>• Missing criteria is displayed under the password field |
| Registration with Missing Required Fields | 1. Navigate to the registration form<br>2. Leave one or more required fields empty<br>3. Submit the form | • An error message is displayed indicating that all required fields must be filled<br>• "Registrarse" button is disabled |
| Cross-Browser and Cross-Device Testing | 1. Perform the above test cases on various browsers (Chrome, Firefox, Safari) and devices (desktop, tablet, mobile) | The registration process functions correctly across all tested browsers and devices |

 ### 3 Bugs Report

| Bug Title | Steps to Reproduce | Expected Result | Actual Result | Severity | Environment |
|-----------|-------------------|-----------------|---------------|-----------|-------------|
| [Password field] - No distinction between capital and lowercase letters | 1. Navigate to the registration form<br>2. Enter a password with only capital letters | "al menos 1 letra en minúscula (a-z)" criteria is not met, so the "Registrarse" button should be disabled | "al menos 1 letra en minúscula (a-z)" criteria is met | Medium | Chrome, MacOS<br>Safari, MacOS<br>Safari, iOS<br>Chrome, iOS |
| [Password field] - "ñ" character not accepted as lowercase letter | 1. Navigate to the registration form<br>2. Enter a numerical password including the "ñ" character | "al menos 1 letra en minúscula (a-z)" criteria is met since the "ñ" character is a lowercase letter | "al menos 1 letra en minúscula (a-z)" criteria is not met | Medium | Chrome, MacOS<br>Safari, MacOS<br>Safari, iOS<br>Chrome, iOS |
| [Registration form] - Terms of agreement shows in English | 1. Navigate to the registration form<br>2. Click "...el acuerdo con contrato de oferta para la moneda elegida" link | Contract should be consistent with the language of the website | Contract is in English | Medium | Chrome, MacOS<br>Safari, MacOS<br>Safari, iOS<br>Chrome, iOS |
| [Email field] - Any string enables "Registrarse" button | 1. Navigate to the registration form<br>2. Type in any string in the email field | "Registrarse" button should be disabled until a valid email format is entered | "Registrarse" button is enabled | Medium | Chrome, MacOS<br>Safari, MacOS<br>Safari, iOS<br>Chrome, iOS |
| [Bonus modal] - Link to bonus page improperly underlined | 1. Navigate to the registration form<br>2. Click the "Bono de bienvenida" selector | The link to the bonus page should be underlined as "bonificación del casino" | "bonificacion del" text is underlined, leaving out the rest of the sentence | Medium | Chrome, MacOS<br>Safari, MacOS<br>Safari, iOS<br>Chrome, iOS |


 ### 4 Feedback/Recommendations

## Accessibility Features

### Observation
The registration page should be accessible to users with disabilities, including compatibility with screen readers and keyboard navigation.

### Recommendation 
Adhere to Web Content Accessibility Guidelines (WCAG) to make the registration process inclusive for all users. This includes providing text alternatives for non-text content and ensuring sufficient color contrast.

## Language Inconsistencies & Incorrect Contract Language

### Observation
There is a contract displayed in English when it is supposed to be in Spanish. This inconsistency can cause confusion, especially for users who may not understand English, making it difficult for them to fully comprehend the terms they are agreeing to.

### Recommendation
- Ensure that all legal documents, including contracts, are displayed in the correct language (Spanish in this case)
- Implement a language detection mechanism that ensures the correct version of the contract is shown based on the user's location or selected language preference
- If a multilingual contract is required, provide an explicit language toggle option rather than switching languages automatically

## Language Flashing Issue

### Observation
Users may momentarily see parts of the registration form in English before it quickly switches to Spanish. This flickering can make the site appear unpolished and impact user trust.

### Recommendation
- Ensure that the page loads the correct language before rendering instead of applying language settings after the content is displayed
- Preload language-specific content to prevent visible language changes after the page has loaded
- Test with slow internet connections to ensure users do not experience content switching delays

## Consistent Branding

### Observation
Maintain consistent branding elements, such as logos, color schemes, and typography, throughout the registration page to reinforce brand identity.

### Recommendation
Ensure that the design of the registration page aligns with the overall branding of JugaBet, providing a cohesive experience for users.
