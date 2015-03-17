#ngTemplate
The ng-template directive lets you create `view partials` for routing without needing to actually link to a physical file. It's a good way to create subpages in apps like CakePHP without needing to get into crazy reloads or routing issues.

## example
The following example declares a `template` and then uses it with the `$routeProvider` on the same page


```html
<div ng-app='myApp'>

	<!-- declare a 'templateURL' via ng-template and the ID tag -->
	<script type='text/ng-template' id='myPartial.html'>
		<h2>Hello, {{user.name}}!</h2>
	</script>
	
	<!-- declare a 'templateURL' via ng-template and the ID tag -->
	<script type='text/ng-template' id='myPartial2.html'>
		<h2>Goodbye, {{user.name}}!</h2>
	</script>
	
	<!-- use that template on the same page! leet haxx -->
	<script type='text/javascript'>
		angular
			.module('myApp')
			.config(['$routeProvider', function($routeProvider){
				$routeProvider
					.when('/hi', {
						templateURL: 'myPartial.html',
						controller : ..
					})
					.when('/bye', {
						templateURL: 'myPartial2.html',
						controller : ..
					})
			}])
	</script>
</div>
```