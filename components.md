---
layout: primary-page
id: components
title: Components
meta: Accessibility, WCAG, Components, Keyboard Accessibility
category: components
status: draft
---

<p>User Interface (UI) components are lists, buttons, and dropdowns. Sometimes they are created with a single HTML element, like a link is. Sometimes they are created with more complex combinations of multiple HTML elements that reference one another, like a select.</p>

<p>Since they can be interacted with, they need to follow <a href="https://wlla.github.io/structure/focus.html">focus requirements and best practices</a> and to be discoverable and operable with a keyboard. Components need have a name, role, and status that can be programmatically set and determined. (A screenreader user relies on these to understand what the component is and how to use it.) Remember that "programmatically" means a computer can determine the name, role, and status and it's not dependent on something like visual proximity.
<p>UI components should follow HTML standards. When we follow HTML standards, keyboard navigation and naming requirements are built in. Avoid making custom widgets that recreating existing components, like using an image and assigning it the role of button. You will have to stuff it full of workarounds, keyboard events, and ARIA, but it still won't work as well as standard out of the box elements.</p>
<p>ARIA can be very extend the accessibility of UI components, but should only ever be used to build on a baseline of accessibility (see the <a href="https://wlla.github.io/components/labels-instructions.html">Labels & Instructions page</a> for examples) or when native HTML elements don't suffice.</p>
<h2>Keyboard Navigation</h2>
<p>Components must all be navigable with standard keyboard inputs or gestures. Remember, this is true for mobile as well as desktop. Android automatically supports keyboard gestures and users with bluetooth keyboard need to access your stuff.</p>
<p>We use keyboard inputs because a variety of input devices map to these inputs. A joystick for example, is going to be mapping to these input devices.</p>
<h2>Code Examples</h2>
<p>The <a href="https://designsystem.digital.gov/">US Gov Design System</a> includes a set of components which have been reviewed for accessibility. It's a good reference.</p>
