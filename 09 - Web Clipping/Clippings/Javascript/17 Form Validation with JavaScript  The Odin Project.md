---
title: "Form Validation with JavaScript | The Odin Project"
source: "https://www.theodinproject.com/lessons/node-path-javascript-form-validation-with-javascript"
author:
published:
created: 2025-07-10
description: "The Odin Project empowers aspiring web developers to learn together for free"
tags:
  - "clippings"
---
Forms are a crucial part of most websites. Almost every major site has sign-up forms, contact forms, search forms and more! Luckily HTML5 and JavaScript have some handy built-in methods. You’ve already learned about validation with HTML and styling validations with CSS in our [Form Validations](https://www.theodinproject.com/paths/full-stack-javascript/courses/intermediate-html-and-css/lessons/form-validation) lesson in the Intermediate HTML and CSS course.

In this lesson, we’ll cover the Constraint Validation API: a way to validate forms on the frontend with JavaScript.

This section contains a general overview of topics that you will learn in this lesson.

- Understand the importance of validation in HTML forms.
- Understand Constraint Validation API for more control over form validation.
- Add validation using only JavaScript.

1. This [tutorial on Form Validation](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_using_javascript) covers how we can use JavaScript to validate forms, including the constraint validation API.
2. It’ll also prove beneficial to go through the [Constraint Validation docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Constraint_validation).
3. For reference, [W3Schools’ page on the JavaScript validation API](https://www.w3schools.com/js/js_validation_api.asp) covers things in a more concise format. These functions were explained in the previous article. Typically, with HTML forms, the inputs are validated upon form submission, but you can use these functions to check validity whenever you like (such as when a user clicks or tabs out of a specific input field).

Go back to your ‘Library’ project and add validation to that form! Don’t let your users submit without filling in all the fields! Don’t forget to use the git branch workflow you learned in [Revisiting Rock Paper Scissors](https://www.theodinproject.com/lessons/foundations-revisiting-rock-paper-scissors) from Foundations to work on a new feature.

Build a browser form which collects Email, Country, Postal Code, Password and Password Confirmation fields. It should use live inline validation to inform the user whether a field is properly filled in or not. That means highlighting a field red and providing a helpful error message until it has been filled in properly.

The form doesn’t need to actually submit, but you should give an error message if the button is pushed with any active errors or unfilled required fields. For the sake of this lesson, make sure the `<form>` element has the [`novalidate` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#novalidate) which will allow you to do **all** of your validation in your JavaScript files. You can still use different `<input>` types, but you will need to use JavaScript to check and report their validity. If all is well and the form is “submitted”, give the user a high five.

1. Set up a blank HTML document
2. Think about how you would set up the different form elements and their accompanying validators. What objects and functions will you need? A few minutes of thought can save you from wasting an hour of coding. The best thing you can do is whiteboard the entire solution before even touching the computer.
3. Write the form elements.
4. Add the JavaScript code that checks validation as the user progresses through the form. When a user leaves a form field, it should automatically validate that field.
5. Test out all possible cases.
6. Don’t forget to style validations with CSS by using the `:valid` and `:invalid` pseudo-classes!

The following questions are an opportunity to reflect on key topics in this lesson. If you can’t answer a question, click on it to review the material, but keep in mind you are not expected to memorize or master this knowledge.

- [What is the importance of validating HTML forms before submitting them to a server?](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#what_is_form_validation)
- [What are the two types of client-side form validation?](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#different_types_of_client-side_validation)
- [How does JavaScript Constraint Validation API provide more control and customization of form validation?](https://developer.mozilla.org/en-US/docs/Learn/Forms/Form_validation#validating_forms_using_javascript)

This section contains helpful links to related content. It isn’t required, so consider it supplemental.

- It looks like this lesson doesn’t have any additional resources yet. Help us expand this section by contributing to our curriculum.

[Improve on GitHub](https://github.com/TheOdinProject/curriculum/edit/main/javascript/javascript_in_the_real_world/form_validation_with_javascript.md) [Report an issue](https://github.com/TheOdinProject/curriculum/issues/new?labels=Status%3A+Needs+Triage&lesson-link=https%3A%2F%2Fwww.theodinproject.com%2Flessons%2Fnode-path-javascript-form-validation-with-javascript&template=suggestion.yaml&title=Form+Validation+with+JavaScript%3A+%3CShort+description+of+your+suggestion%3E) [See lesson changelog](https://github.com/TheOdinProject/curriculum/commits/main/javascript/javascript_in_the_real_world/form_validation_with_javascript.md)

## Support us!

## The Odin Project is funded by the community. Join us in empowering learners around the globe by supporting The Odin Project!

[Learn more](https://www.theodinproject.com/support_us) [Donate now](https://opencollective.com/theodinproject/donate?amount=5)