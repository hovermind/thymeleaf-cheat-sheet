## Concatenation `+`
```
<div th:with="foo=${ ... }">

	<h2 th:text="${ foo.bar + 'test' }"></h2>

	<p>[[${ 'Description: ' + foo.baz }]]</p>
	
</div>
```

## Literal Substitions `| |` (Interpolation)
```
<p th:text="|${foo} ${bar}|"></p>

<div th:with="foo=${ ... }">

	<a th:href="@{ |/product/${ foo ne null ? 'details/' + foo : '' }| }" >Product Details</a>
	
</div>
```

**Note:** `th:text="${foo} ${bar}"` would not work, you have to use `| |` to get space in between (or use `th:text="${foo + ' ' + bar}"`)

