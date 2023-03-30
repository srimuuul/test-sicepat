# Positive Testcases

```
Feature: Login user
Scenario: Login user success
  GIVEN user on Login page
  WHEN user input "standard_user" in the "Username" field
  AND user input "secret_sauce" in the "Password" field
  AND user click the "Login" button 
  THEN user will be direct to "Products" page
```

```
Feature: Add to cart
Scenario: Add to cart on the detail product by click image product
  Given user on Products page
  When user click on image product "Sauce Labs Backpack"
  THEN user will be show the page Detail Sauce Labs Backpack product
  AND user click the "Add to cart" button
  THEN product success add to cart, on icon cart will be show count badgewand button "Add to cart" changes to "Remove"
```

```
Feature: Add to cart
Scenario: Add to cart on the detail product by click title product
  Given user on Products page
  When user click on title product "Sauce Labs Backpack"
  THEN user will be show the page Detail Sauce Labs Backpack product
  AND user click the "Add to cart" button
  THEN product success add to cart, on icon cart will be show count badgewand button "Add to cart" changes to "Remove"
```

```
Feature: Add to cart
Scenario: Add to cart on Products page
  Given user on Products page
  When user click "Add to cart"
  THEN product success add to cart, on icon cart will be show count badgewand button "Add to cart" changes to "Remove"
```

```
Feature: Checkout
Scenario: Checkout product
  Given user on Products page
  When user click an icon cart
  THEN will be direct to Your Cart page
  AND user click "Checkout" button
  THEN user will see the "Chekout: Your Information" page
  AND user input "testing" in the "First Name" field
  AND user input "testing" in the "Last Name" field
  AND user input "40233" in the "ZIP/Postal Code" field
  AND user click "Continue" button
  THEN user will see the "Checkout: Overview" page
  AND user click "Finish" button
  THEN user will see "Checkout: Complete!" page with message "Thank you for your order!", and count badge on icon cart already pass
```


# Regression

```
Feature: Checkout
Scenario: Checkout product
  GIVEN user is already logged in 
  AND user is on Products page
  When user click "Add to cart"
  THEN product success add to cart, on icon cart will be show count badgewand button "Add to cart" changes to "Remove"
  AND user click an icon cart
  THEN will be direct to Your Cart page
  AND user click "Checkout" button
  THEN user will see the "Chekout: Your Information" page
  AND user input "testing" in the "First Name" field
  AND user input "testing" in the "Last Name" field
  AND user input "40233" in the "ZIP/Postal Code" field
  AND user click "Continue" button
  THEN user will see the "Checkout: Overview" page
  AND user click "Finish" button
  THEN user will see "Checkout: Complete!" page with message "Thank you for your order!", and count badge on icon cart already pass
```


# Negative Testcases

```
Feature: Login user
Scenario: Login user with wrong Username
  GIVEN user on Login page
  WHEN user input "test" in the "Username" field
  AND user input "secret_sauce" in the "Password" field
  AND user click the "Login" button 
  THEN user failed to Login and will show warning message
```

```
Feature: Login user
Scenario: Login user with wrong Password
  GIVEN user on Login page
  WHEN user input "standard_user" in the "Username" field
  AND user input "secret_sauces" in the "Password" field
  AND user click the "Login" button 
  THEN user failed to Login and will show warning message
```

```
Feature: Login user
Scenario: Login user with not registered account
  GIVEN user on Login page
  WHEN user input "testing" in the "Username" field
  AND user input "testing" in the "Password" field
  AND user click the "Login" button 
  THEN user failed to Login and will show warning message
```