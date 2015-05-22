#ngChange
The ng-change directive fires any time its associated `ng-model` field's value is changed. By default it triggers for EVERY single change. For example if the field value is changed from `foo` to `bar` it will fire at least `4` times one for each of the following `delete, value = 'b', value = 'ba', value = 'bar'`.

* `ng-model` is **REQUIRED**

Quick Links

* [make ngChange wait before firing](#update-with-delay)
* [make ngChange wait until onBlur before firing](#update-with-updateon)

###<a name='update-with-delay'></a> Update with Delay
The following example shows how to force the `ng-change` to only fire if no changes have occurred in a certain amount of time.

```html

<div ng-app='myApp'>
	
	<!-- only fire ng-change if CHANGED and NO CHANGES IN PAST 1000ms -->
	<input ng-model='foo' ng-change="console.log(foo)" ng-model-options="{debounce:1000}"/>
	<span>{{foo}}</span>
	
</div>

```

###<a name='update-with-updateon'></a> Update onChange and onBlur
The following example shows how to force the `ng-change` to only fire if the field changed (`'ng-change'`) AND the user has left the field (`'blur'`)

```html
<div ng-app='myApp'>
	
	<!-- only fire ng-change if CHANGED and BLUR -->
	<input ng-model='foo' ng-change="console.log(foo)" ng-model-options="{updateOn:'blur'}"/>
	<span>{{foo}}</span>
	
</div>
```