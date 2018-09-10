## Dynamic Fragment Name & Params
`PageRoleEnum.java`
```
public enum PageRoleEnum {
	A, B
}
```

`fragments.html`
```
<div th:fragment="A(title)">

	<div th:with="title_lowercase=${#strings.toLowerCase(title)}" class="flex" >
	
		<img alt="" th:src="@{'icons/top_' + ${title_lowercase} + '.png'}" />
		
		<h3>
			<a th:href="@{'/' + ${title_lowercase} }">[[${#strings.capitalize(title_lowercase)}]]</a>
		</h3>
		
	</div>

	<div class="service_item_content">

	</div>

</div>

<div th:fragment="B(title)">

	<div th:with="title_lowercase=${#strings.toLowerCase(title)}" class="flex" >
	
		<img alt="" th:src="@{'icons/top_' + ${title_lowercase} + '.png'}" />
		
		<h3>
			<a th:href="@{'/' + ${title_lowercase} }">[[${#strings.capitalize(title_lowercase)}]]</a>
		</h3>
		
	</div>

	<div class="service_item_content">

	</div>

</div>
```

**Using Fragment Dynamically**
```
<th:block th:each="item : ${T(MyPackage.PageRoleEnum).values()}">

	<div th:insert="~{ partials/fragments :: __${item}__(title=${item}) }>

	</div>
	
	// or conditionally
	<div th:insert="${ #authorization.expression( 'hasAuthority(''' + item +''')' ) } ? ~{ fragments :: A } : ~{ }" >

	</div>
	
</th:block>
```
