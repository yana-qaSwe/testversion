
# <a name="up" />QA_Portfolio

The portfolio includes some projects completed during QA Engineer training.

[Web Testing](#web-testing)<br>


[Mobile Testing](#mobile-testing)<br>


[API Testing](#api-testing)<br>


[Database](#data-bases)<br>



## <a name="web-testing" />Web Testing

### Objective

Verify the correctness of the website layout and the functionality of key modules for Demoshoping.ru.

**1. Study Requirements:**

Review the requirements for the Demoshoping.ru service. Analyze the layout requirements, including design mockups and UI component specification

**2. Test Documentation for Layout**

- Analyze the layout requirements: visual appearance and correct positioning
- Make sure the checklist includes: compliance with mockups (visual inspection, not “pixel-perfect”); responsiveness and proper display on different screen resolutions.

Create a detailed checklist to verify the visual aspects of the website

**3. Test Registration and Login Modules**

Verify the registration and login functionality, including user authorization.


**4. Testing and Bug Reports**

During testing, mark the test results as PASSED or FAILED. If a test is FAILED, create a bug report and record its ID in the corresponding results table.

### Solution

**1. Check-list for Layout**

| № | Description | Windows 10 Pro Version 22H2 Google Chrome 138.0.7204.101| ID bag-report |
|:--:|:-----------|:-----:|:-------:|
|1|After the page loads, there are no errors or warnings in the console|	PASSED| -|
|2|	The website's favicon is displayed on the browser tab|	FAILED|	[BUG-2608](#BUG-2608)|
|3|	The page title is displayed correctly on the browser tab and in the address bar|	PASSED	|	-|
|4|The website header is implemented according to the design and is fully visible. The items "Catalog", "About Us" and "Contacts" in the header function as links that open the corresponding service pages when clicked|	PASSED|	-|
|5|	The "Min. price" input field is displayed according to the design|	PASSED|	-|
|6|	The "Max. price" input field is displayed according to the design|	PASSED	|	-|
|7|	The number input spinners for "Max price" and "Min price" are displayed correctly|PASSED	| -|
|8|	The "All categories" dropdown is displayed as per the design and functions correctly|PASSED| -|
|9|	The "All manufacturers" dropdown is displayed as per the design and functions correctly|	PASSED	|	-|
|10|	The checkbox "Free delivery" is displayed according to the design and works correctly|PASSED	| -|
|11|	The "Apply filters" button is displayed according to the design and works correctly; clicking the button triggers a single action; repeated clicking does not trigger the action again|	PASSED	|	-|
|12|	The "Reset filters" button is displayed according to the design and works correctly; clicking the button triggers a single action; repeated clicking does not trigger the action again|	PASSED|	-|
|13|	All texts do not contain spelling errors|	PASSED	|	-|
|14|	The "Registration/Login’" button is placed according to the design and is fully visible; clicking the button opens the Registration/Login page in a new tab|	PASSED|	-|
|15|	The Demoshopping copyright and the "Terms of Use" link are placed according to the design and are fully visible; clicking the link opens the Demoshopping Terms of Use page in a new tab|	PASSED|	-|
|16|	The "Sort" dropdown menu is displayed according to the design; clicking it opens and closes the menu; each option is clickable and triggers the correct action|	PASSED |-|
|17|	Placeholders: the Min.price and Max.price input fields contain placeholders; the placeholder disappears when the user starts typing; it reappears if the field is cleared; the placeholder looks different from the user-entered data; all form placeholders have a consistent appearance|	PASSED|	-|
|18|	Spinners: all spinners are displayed when the field is focused; the spinners function correctly|	FAILED	|[BUG-2610](#BUG-2610)|
|19|	Error messages are positioned according to the design and are fully visible|	PASSED	|	-|
|20|	The quantity input fields on the product cards are displayed according to the design; negative values or non-numeric values are not accepted|	FAILED|	[BUG-2611](#BUG-2611)|
|21|	The "Add to Cart" buttons on each product card are positioned according to the design and displayed correctly; the button label matches its functionality|	PASSED|	-|
|22|	Paging design matches the mockup and functions correctly|PASSED|	-|
|23|	Input fields: allow editing of entered data; field labels correspond to their logic; input data formats meet the requirements|	PASSED|	-|
|24|	Error messages are positioned according to the design and fully visible|	PASSED|-|
|25|	The page layout adapts to screen size changes|	FAILED|	[BUG-2614](#BUG-2614git )|

**3. Bug-reports**

<details>
<summary>BUG-2608: The website's favicon isn't displayed on the browser tab</summary>

***

**Steps:**

1. Open demoshopping.ru.

**Actual result**: the website's favicon isn't displayed on the browser tab.

**Expected result**: the website's favicon is displayed on the browser tab.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Low

***

</details>

<details>
<summary>BUG-2614:Pagination is not responsive and shifts off-screen when resizing the layout</summary>

***

**Steps:**

1. Open Demoshopping.ru
2. Resize the browser window.
3. Observe the pagination block.

**Actual Result**: pagination shifts off-screen and becomes partially hidden.

**Expected Result**: pagination remains visible and correctly aligned within the viewport.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Medium

***

</details>

<details>
<summary>BUG-2611: The quantity input fields on the product cards on the main page accept invalid characters</summary>

***

**Steps:**

1. Open Demoshopping.ru
2. In the quantity input field on any product card, enter invalid characters such as "+", "-", ".", ",'.
3. Click "Add to card"


**Actual result**: the product was added to the card.

**Expected result**: negative values should be rejected.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Higt

***

</details>

<details>
<summary>BUG-2610: The "Min.price" and "Max.price" input fields accept negative values on the main page</summary>

***

**Steps:**

1. Open Demoshopping.ru
2. Enter -75 in the "Min.price" or "Max.price" field.
3. Click "Apply a filter".

**Actual result**: the request is processed, and the filtering occurs as if the negative value were valid.

**Expected result**: negative values should be rejected.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Higt

***

</details>

[Back to top](#up)
