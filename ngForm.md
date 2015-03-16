#ngForm

1. [Validation States (CSS)](#validation-states-css)
2. [Subforms](#subforms)
  3. [Subform validation](#subform-validation) 

##Validation States (CSS)
[[link]](https://docs.angularjs.org/guide/forms) The following CSS classes are linked to the different validation states of input on forms (and the forms themselves).

- `ng-valid`: the model is valid
- `ng-invalid`: the model is invalid
- `ng-valid-[key]`: for each valid key added by `$setValidity`
- `ng-invalid-[key]`: for each invalid key added by `$setValidity`
- `ng-pristine`: the control hasn't been interacted with yet
- `ng-dirty`: the control has been interacted with
- `ng-touched`: the control has been blurred
- `ng-untouched`: the control hasn't been blurred
- `ng-pending`: any `$asyncValidators` are unfulfilled

##Subforms
Subforms are a great way to get localized validation for different sections of a larger form.
Subforms do not need to be actual `<form>`s , nor do they need to be nested inside a `<form>`

###Subform validation
Subforms track thier own validation separate from the main form.

```html
<form name='mainForm'>
	<div ng-form="UserSubform"> <!-- this creates a subform -->
		<input ng-model="user.name" placeholder="your name" required />
	</div>
</form>
	
Main Form $valid     : {{ mainForm.$valid }} true iif subforms are valid
UserSubForm $valid   : {{ UserSubform.$valid }} true iif all required fields are valid
UserSubForm $invalid : {{ UserSubform.$valid }} true iif any required fields are invalid

```
