Assistive technologies don't interact with the DOM directly, they actually interact with the  Accessibility tree, which is a technology similar to the DOM.

## Accessibility Tree
Each node in the accessibility tree has:
- name: a title for the node
- description: further description of the node
- role: function of the node. (i.e checkbox)
- state: i.e checked/unchecked)

## WAI-ARIA
  The "Web Accessibility Initiative - Accessible Rich Internet Applications" specification  for accessible HTML created by W3C.This contains a set of HTML attributes that can be  added to provide extra information to the accessibility tree.
  
  ARIA attributes are grouped in tree categories: roles, properties and state
  
### Roles
What the element is doing. It can be be broken down into a few subgroups:
- Landmark: Major content area the will receive focus, like banner, main, navigation. Some HTML tags receive this role automacally, but it can be done manually.
```html
<div role="banner">
	<h1>My Accessible Webpage</h1>
</div>
```
- Structure: Document structural information. (i.e tooltip, list, table)
```html
<section role="list">
	<div role="listitem">First item</div>
	<div role="listitem">Second item</div>
	<div role="listitem">Third item</div>
</section>
```
- Widget: Interactive elements. (i.e tab, searchbox, button) Some HTML tags receive this role automacally, but it can be done manually.
```html
<div role="button">Click Me!</div>
```
- Window: Sub-windows in the browser. Set content apart from the page. (dialog and alert-dialog)
```html
<div role="dialog" aria-labelledby="title">
	<h2 id="title">Successfully saved changes</h2>
	<button>Dismiss</button>
</div>
```
- Live Region: Regions with dinamically changing content.
	1. Roles: i.e timer, log, alert
	```html
	<ol role="log">
		<li>Chat message 1</li>
		<li>Chat message 2</li>
		<li>Chat message 3</li>
	</ol>
	```
	2. Attributes (aria live): Tell how often the content will change
		- off: Don't announce changes
		- polite: Announce changes when idle
		- assertive: Announce changes as soon as possible
	```html
	<div aria-live="polite">
		My content will change!
	</div>
	```
### Properties
 Extra meaning and characteristics of the elements. (i.e labels)
 - aria-label: Label not visible on UI
 - aria-labelledby: Another element as a lable, passed by ID
 - aria-descrition: More detail than labels
 - aria-describedby: Another element as a description, passed by ID
 ```html
<div role="dialog" aria-labelledby="title">
	<h2 id="title">Successfully saved changes</h2>
	<button>Dismiss</button>
</div>
```
 
### States
Current state of the element.
- aria-checked
- aria-disabled: can't interact with
- aria-expaded
- aria-hidden
- aria-pressed
- aria-selected
```html
<div role="checkbox" aria-checked="true">
	I'm checked
</div>
```

#### Other concerns
- Browser compatibility
- CSS Accessibility: use contrast, legible fonts, mobile support, etc.
- Internacionalization (i18n)
	- Language support
	- Test with different "style" languages