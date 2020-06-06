---
layout: primary-page
id: forms
title: Forms
meta: Accessibility, WCAG, Components, Keyboard Accessibility
category: components
status: draft
---
I'm using form to describe an interface that sends data to another place.
## Orientation
There is some basic, high-level information that people should be able to tell about your form.

- What is this form?
- What info will I need to complete this form?
- What happens when I hit "submit"? What do I need to do next or what can I expect to happen?
- Am I able to use this form? If there are eligibility requirements, what are they? If this isn't the form for me, where can I find the right one?
- When I finish this form, will I have a record of the transaction?

### Required Fields
Make sure to mark the required fields. Do this in the text label, with the word "Required" or a "\*". Include this in the mark-up as well.

In HTML, there are two ways to do this: <code>required</code> attribute or the <code>aria-required="true"</code> attribute. With the HTML attribute, right now, some screenreaders announce that information as soon as you enter an input, which can be irritating. Hopefully will be updated.

### Required Formats and Instructional Text
### Placeholder Text
Placeholder text: Placeholder text is confusing. Avoid it. Browsers will often render in too low color contrast ratio and isn't reliably picked up with screenreaders. Cognitively, it can be confusing and make it seem like the form is pre-filled. Also, placeholder text isn't persistent, so it isn't that useful of a reference.
Placeholder text is never serves as a label, instruction, or error message. It can only ever be supplemental to those required fields. Again, best to just avoid.

### Progress & Time Required
Progress: You may have a long, complex, or branching form that you decide to break into multiple pages. If you do, give people a sense of how long it will take to complete the form, how long the form is, and what information they will need up-front. You should also let them know if there are time limits or if they will be able to save their progress and return. (Think about an application for a job or school.)
Give people a progress bar so they know how far they have progressed.

### Validation
Keep in mind the difference between validation and required fields. An email may be optional in a form, but it still needs to be entered as a valid email address. Part of helping users avoid errors is providing validation when you can.
## Labels
Persistent label. You want people to use your form, right? Give it a label!! This label must be programmatically associated with the form control!
Fieldset: a fieldset / legend combo groups sections of forms. They are a requirement for radio buttons. They can help organize the form. Consider a form that has an address and mailing address section each with inputs for  address, city, state, and zip. Using legend and fieldset means those sections are labelled meaningfully.
Instructional text and inline error messages: don't overwrite, but can use the same section.
Dynamic forms: sometimes, you'll have a single page of a form where sections appear and disapear based on what you've entered. (maybe the filters in ravelry?)
## Error Messages
Forms are looking for specific types of input. When a user puts is missing information or uses the wrong format, we can help them!
WCAG has a whole section on error messages to "help users avoid and correct mistakes", <a href="https://www.w3.org/WAI/WCAG21/quickref/?showtechniques=147#input-assistance">Guideline 3.3 - Input Assistance</a>. The guideline has six success criteria.
Server-side error messages versus client-side error messages and validation
In-line error messages versus aggregated error messages. Client side validation means the user gets the info faster. It also means their computer is doing some extra work and you're probably building some js.
When you build a form, first make sure you're doing server side validation. That's how you'll serve no-JS users. Then build client-side validation as an enhancement.
You want the error messages to be on the same page so people can reference them. I've seen sites where, after I hit "Submit", the error message showed up as a modal. That's not great because then I would have to remember which field needs correcting when I go back to the form.
Have two types of error messages: aggregated and in-line. If you submit a form with errors, provide an error message that 1. explains what it is aka i am an aggregated error message, recieves focus, lists and links - lists all the errors on the page and links to them. In-line error messages and states are associated with individual fields. There could be visual treatment, like using the color red and there should also be text that 1. explains that there is an error; 2. suggests how to fix it. 3. includes any existing instructional text.
If you are validating client-side make sure that validation happens onBlur. OnBlur means that the focus moves out of the field. If you had this triggering when you enter, it would be obnoxious. Don't be obnoxious. inline can happen onblur
### Instructional text
When is it needed and where? When something specific is required that isn't clear in the label or that users could use support in. When you label an input for a zipcode, you expect a certain format.
You can connect your instructional text with your label programmatically with the aria-labelledby attribute.
Any error message should include rather than overwrite instructional text.
### Organizing Your Form wiht Fieldsets
Example of work address and shipping address
## Time Limits
Avoid imposing time limits unless it is essential to the activity or is for security reasons. Be thoughtful about when to use a time-limit. When a time-limit is short, it can cause cognitive strain. Give a countdown clock to a form, and you'll get higher error rates. While a clock is dynamic content, never wrap it in an aria-live; it would be enourmously distracting and disruptive.
Make sure your time-outs follow <a href="https://www.w3.org/WAI/WCAG21/quickref/#enough-time">WCAG Guideline 2.2 - Enough Time</a>. At a minimum, <a href="https://www.w3.org/WAI/WCAG21/quickref/#timing-adjustable">2.2.1 Timing Adjustable</a>, a level A success critiera with straightforward rules on time limit duration and adjustability.
## CAPTCHA
Avoid CAPTCHA (Completely automated public Turing test). CAPTCHA manifest as little tasks to perform, like identifying features in images or sound, or clicking a checkbox. The idea behind it is to block malicious software like bots from spamming or otherwise being bad actors. The problem is that the CAPTCHA aren't so accessible in format and they will problematically lump good, assistive technology like screenreaders into the "bad software" bucket.
## Screenreaders & Forms
Screenreaders have a form mode they enter. Screenreaders use a number of keyboard shortcuts; For instance, with Jaws, "B" will navigate a user to all the buttons on a page. These shortcuts aren't useful if you're trying to type "Brown Bear" info a form asking your favorite animal. Forms mode means that the keystrokes will write the actual glyphs rather than trigger a shortcut.

Screenreader users don't necessarily use the tab key for navigation. (Though that is a common perception.) The tab key is useful in forms to jump quickly through fields, provided they are accessibly labelled!
