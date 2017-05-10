---
layout: essay
type: essay
published: false
title: "Meteor Gotchas"
date: 2017-03-09
labels:
  - Software Engineering
  - Meteor
---

## Endless Imports

It's been about two weeks of learning Meteor, the open-source JavaScript web framework.  Over these two weeks, I have just scratched the surface of Meteor and have already encountered my fair share of problems and roadblocks. Like learning any new language, framework, or technology, practice and constant repetition makes perfect. One problem I encountered often starting out was the need for multiple import statements in the various JavaScript files of my projects. Each directory containing one or more JS files must have an index.js file which holds all the import statements for each JS file in that directory. Then, each directory must be imported by the main.js file in the client directory, server directory, or both. On top of that, there are other import statements needed in the lower level JS files to allow for use of certain variables and template helpers. At times, I would run my web app locally on a browser to test my code, however, sometimes the data that I expected to see was not present. The problem was always a missing import statement. Encountering these problems forced me to really think about and understand how each import statement works and why they are so important when using Meteor.

## Simple Syntax

Another problem I recently encountered had to deal with forms and form submission. In one project, I was attempting to implement a 'Submit' button, that when the form was successfully filled, would route the app back to the home page, where the new form submission would be displayed. However, the problem I had was that the page would not respond once the submit button was pressed, even when the form was correctly filled. Here was my template class in the JavaScript file:

```
Template.Add_Contact_Page.events({
  'submit .contact-data-form'(event, instance) {
    event.preventDefault();
    // Get name (text field)
    const first = event.target.First.value;
    const last = event.target.Last.value;
    const address = event.target.Address.value;
    const telephone = event.target.Telephone.value;
    const email = event.target.Email.value;

    const newContactData = { first, last, address, telephone, email };
    // Clear out any old validation errors.
    instance.context.resetValidation();
    // Invoke clean so that contactData reflects what will be inserted.
    ContactsSchema.clean(newContactData);
    // Determine validity.
    instance.context.validate(newContactData);
    if (instance.context.isValid()) {
      Contacts.insert(newContactData);
      instance.messageFlags.set(displayErrorMessages, false);
      FlowRouter.go('Home_Page');
    } else {
      instance.messageFlags.set(displayErrorMessages, true);
    }
  },
});
```

And here was the line which invokes this event in the HTML file:

```
<div class="ui submit button">Submit</div>
```

It turns out, the only problem was a syntax error in the HTML line, which needed to be this instead:

```
<button class="ui submit button">Submit</button>
```

I've learned that a simple syntax error can solve a big problem.
