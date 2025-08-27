
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
|20|	The quantity input fields on the product cards are displayed according to the design; negative values or non-numeric values are not accepted|	FAILED|	[BUG-2611](#BUG-2611), [BUG-2725](#BUG-2725)|
|21|	The "Add to Cart" buttons on each product card are positioned according to the design and displayed correctly; the button label matches its functionality|	PASSED|	-|
|22|	Paging design matches the mockup and functions correctly|PASSED|	-|
|23|	Input fields: allow editing of entered data; field labels correspond to their logic; input data formats meet the requirements|	PASSED|	-|
|24|	Error messages are positioned according to the design and fully visible|	PASSED|-|
|25|	The page layout adapts to screen size changes|	FAILED|	[BUG-2614](#BUG-2614)|

**2. Test-cases: Registration and Authorization**

<details>
<summary>ID-1: Registration with a valid login and a valid password</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login | -	| The login page is opened
2 | Enter a valid login in the "Login" field | log2_	| The login is displayed without an error message
3 | Enter a valid password in the "Password" field | 12345678q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| User is successfully registered and redirected to main page

**Result**: FAILED

**ID Bug-report**: [BUG-2709](#BUG-2709)

***

</details>

<details>
<summary>ID-2: Registration with minimum allowed characters for login</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login with 3 characters in the "Login" field | lo2	| The login is displayed without an error message
3 | Enter a valid password in the "Password" field | 12345678q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| User is successfully registered and redirected to main page

**Result**: FAILED

**ID Bug-report**: [BUG-2709](#BUG-2709)

***

</details>

<details>
<summary>ID-3: Registration with minimum allowed characters for password</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a valid login in the "Login" field | log1	| The login is displayed without an error message
3 | Enter a password with 8 characters in the "Password" field | 1234567q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| User is successfully registered and redirected to main page

**Result**: FAILED

**ID Bug-report**: [BUG-2709](#BUG-2709)

***

</details>

<details>
<summary>ID-4: Check Registration: Registration with special characters except "_" in the login</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login with 2 characters in the "Login" field | log2@	| The login is displayed without an error message
3 | Enter a valid password in the "Password" field | 12345678q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The username must contain 3 to 15 characters and can include letters, numbers, and symbols: _." is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-5: Check Registration: Invalid login below minimum length</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login with invalid symbols in the "Login" field | log2@	| The login is displayed without an error message
3 | Enter a valid password in the "Password" field | 12345678q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The username must contain 3 to 15 characters and can include letters, numbers, and symbols: _." is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-6: Check Registration: Invalid login above maximum length</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/loginn | -	| The login page is opened
2 | Enter a login with 16 characters in the "Login" field | 1234567890Odtcps	| The login is displayed without an error message
3 | Enter a valid password in the "Password" field | 12345678q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The username must contain 3 to 15 characters and can include letters, numbers, and symbols: _." is displayed

**Result**: FAILED

**ID Bug-report**: [BUG-2708](#BUG-2708)

***

</details>

</details>

<details>
<summary>ID-7: Check Registration: Invalid password below minimum length</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a valid login in the "Login" field | log2_	| The login is displayed without an error message
3 | Enter a password with 7 characters in the "Password" field | 123456q	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The password must be at least 8 characters long, including at least one letter and one number." is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-8: Check Registration: Registration with numeric-only password</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a valid login in the "Login" field | log2	| The login is displayed without an error message
3 | Enter a numeric-only password in the "Password" field | 123456789	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The password must be at least 8 characters long, including at least one letter and one number" is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-9: Check Registration: Registration with alphabetic-only password</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a valid login in the "Login" field | log2	| The login is displayed without an error message
3 | Enter a alphabetic-only password in the "Password" field | abcdefghi	| The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "The password must be at least 8 characters long, including at least one letter and one number" is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-10: Registration with empty fields</summary>

***

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a valid login in the "Login" field | -	| The "Login" field is empty
3 | Leave the "Password" field empty| -	| The "Password" field is empty
4 | Click the "Sign in" button | -	| The tooltip "Fill in the field" is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-11: Registration with existing user</summary>

***
**Pre-conditions:**

User is already registered
Login: log2_
Password: 12345678q

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login from pre-conditions in the "Login" field| log2_ | The login is displayed without an error message
3 | Enter a password from pre-conditions the "Password" field| 12345678q | The password is displayed without an error message
4 | Click the "Sign in" button | -	| The error message "An account with this login/password already exists" is displayed

**Result**: PASSED

***

</details>

<details>
<summary>ID-12: Login with valid data</summary>

***
**Pre-conditions:**

User is already registered
Login: log2_
Password: 12345678q

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login from pre-conditions in the "Login" field| log2_ | The login is displayed without an error message
3 | Enter a password from pre-conditions the "Password" field| 12345678q | The password is displayed without an error message
4 | Click the "Log in" button | -	| The user is redirected to the homepage

**Result**: PASSED

***

</details>

<details>
<summary>ID-12: Login with an invalid login and a valid password</summary>

***
**Pre-conditions:**

User is already registered
Login: log2_
Password: 1234578q

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter an invalid login in the "Login" field| log | The login is displayed without an error message
3 | Enter a password from pre-conditions the "Password" field| 12345678q | The password is displayed without an error message
4 | Click the "Log in" button | -	| The error message "Incorrect username or password" is displayed

**Result**: FAILED

**ID Bug-report**: [BUG-2707](#BUG-2707)

***

</details>

</details>

<details>
<summary>ID-12: Login with a valid login and an invalid password</summary>

***
**Pre-conditions:**

User is already registered
Login: log2_
Password: 1234578q

**Steps**:
№ | Action| Input data | Expected result
:--:|:--|:---|:----
1 | Open the https://qa.demoshopping.ru/login| -	| The login page is opened
2 | Enter a login from pre-conditions in the "Login" field| log2_ | The login is displayed without an error message
3 | Enter an invalid password from pre-conditions the "Password" field| 123456789 | The password is displayed without an error message
4 | Click the "Log in" button | -	| The error message "Incorrect username or password" is displayed

**Result**: FAILED

**ID Bug-report**: [BUG-2707](#BUG-2707)

***

</details>


**3. Bug-reports**

<a name="BUG-2608" />
<details>
<summary>BUG-2608: The website's favicon isn't displayed on the browser tab</summary>

***

**Steps:**

1. Open qa.demoshopping.ru

**Actual result**: the website's favicon isn't displayed on the browser tab.

**Expected result**: the website's favicon is displayed on the browser tab.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Low

***

</details>

<a name="BUG-2614" />
<details>
<summary>BUG-2614: Pagination is not responsive and shifts off-screen when resizing the layout</summary>

***

**Steps:**

1. Open qa.demoshopping.ru
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

<a name="BUG-2611" />
<details>
<summary>BUG-2611: The quantity input fields on the product cards on the main page accept invalid characters</summary>

***

**Steps:**

1. Open qa.demoshopping.ru
2. In the quantity input field on any product card, enter invalid characters such as "+", "-", ".", ",'.
3. Click "Add to cart"


**Actual result**: the product was added to the cart.

**Expected result**: negative values should be rejected.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Higt

***

</details>

<a name="BUG-2725" />
<details>
<summary>BUG-2725: The user can add a zero quantity of the product to the cart</summary>

***
**Pre-conditions:**

The user is authorized

**Steps:**

1. Open qa.demoshopping.ru
2. Navigate to any product
3. Change the quantity of the product by zero input
4. Click "Add to cart"


**Actual result**: error message is not appeared. The product is added to the cart.

**Expected result**: error message is appeared. The product is not added to the cart.

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: Higt

***

</details>

<a name="BUG-2610" />
<details>
<summary>BUG-2610: The "Min.price" and "Max.price" input fields accept negative values on the main page</summary>

***

**Steps:**

1. Open qa.demoshopping.ru
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

<a name="BUG-2708" />
<details>
<summary>BUG-2708: Registration: Invalid login length (16) leads to server error</summary>

***

**Steps:**

1. Open qa.demoshopping.ru/login
2. Click the button “Registration / Log in” 
3. Enter 16 characters in the login field in the Registration section
4. Enter a valid password 
5. Click the “Sign in” button 

**Actual result**: invalid login length (16) leads to server error

**Expected result**: the user sees the message: “The username must contain 3 to 15 characters and can include letters, numbers, and symbols: _"

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: High

***

</details>

<a name="BUG-2709" />
<details>
<summary>BUG-2709: Registration: User is not authorized after registration</summary>

***

**Steps:**

1. Open qa.demoshopping.ru/login
2. Enter a valid login in the login field in the Registration section
3. Enter a valid password 
4. Click the “Sign in” button 
5. Try to open the "Cart" tab

**Actual result**: the user is not authorized

**Expected result**: The user is authorized and redirected to the main page

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: High

***

</details>

<a name="BUG-2707" />
<details>
<summary>BUG-2709: Login: wrong credentials show incorrect error message</summary>

***

**Steps:**

1. Open qa.demoshopping.ru/login
2. Enter an invalid login or password in the Login section 
3. Click the “Log in” button 

**Actual result**: an incorrect message is displayed: “An error occurred while processing the request”

**Expected result**: the message displayed should be: “Incorrect username or password” 

**Environment:**

Windows 10 Pro Version 22H2

Google Chrome 138.0.7204.101<br>

**Attachments**: [authCard.webm]

**Priority**: High

***

</details>


[Back to top](#up)
