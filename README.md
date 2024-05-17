# Angular Project Features

This document details the implementation of various dynamic features in an Angular application using directives and pipes. Each feature is designed to enhance the interactive elements of a web application.

## Features Overview

1. **ColorTime Button** - An attribute directive that changes the background color of a component every half second.
2. **Temporary Ads** - A structural directive that makes an advertisement disappear after 10 seconds.
3. **Form Validation** - Validation that ensures all fields in a form are filled out before submission.
4. **Age Calculation Pipe** - A pipe that calculates age from a selected date after login.

## Detailed Implementation

### 1. ColorTime Button

- **Type:** Attribute Directive
- **Behavior:** Changes the background color of a target component every 0.5 seconds when clicked.
- **Implementation Notes:** Use an array of colors and iterate over it each time the button is clicked, cycling back to the start upon reaching the end.

### 2. Temporary Ads

- **Type:** Structural Directive
- **Behavior:** Automatically removes an advertisement from the DOM 10 seconds after it renders.
- **Implementation Notes:** Use `setTimeout` within the directive to clear the content after a specified interval.

### 3. Form Validation

- **Type:** Form Handling
- **Behavior:** Prevents form submission unless all fields are completed.
- **Implementation Notes:** Utilize Angular's built-in `Validators.required` on all form controls to enforce this rule.

### 4. Age Calculation Pipe

- **Type:** Pipe
- **Behavior:** Calculates and displays age based on the user's birthdate entered through a date picker post-login.
- **Implementation Notes:** Implement a custom pipe that takes the birthdate as input and outputs the age by comparing the date provided to the current date.

## Usage Examples

Below are brief examples of how each component might be implemented or used in a template:

```html
<!-- ColorTime Button Usage -->
<button appColorTime>Change Color</button>

<!-- Temporary Ads Usage -->
<div *appTemporaryAd>
  <p>Special Sale - Limited Time Offer!</p>
</div>

<!-- Form Validation Usage -->
<form [formGroup]="myForm" (ngSubmit)="submitForm()">
  <input formControlName="username" required>
  <input formControlName="password" required>
  <button type="submit" [disabled]="!myForm.valid">Login</button>
</form>

<!-- Age Calculation Pipe Usage -->
<p>Your Age: {{ birthdate | calculateAge }}</p>
