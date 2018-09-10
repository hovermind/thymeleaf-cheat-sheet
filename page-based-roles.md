## Page Based Roles
#### Enum that Represents both Roles and Page Names
`PageRoleEnum.java`
```
public enum PageRoleEnum {
	A, B
}
```

#### Authorize Requests Dynamically in Security Config
`MySecurityConfig.java`
```
@Configuration
public class MySecurityConfig extends WebSecurityConfigurerAdapter {

	@Override
	protected void configure(HttpSecurity http) throws Exception {
	
		// ... ... ... ...
	
		String pageUrl = "";
		String pageUrlWildcard = "";
		String pageRole = "";
		for(PageRoleEnum item : PageRoleEnum.values()) {
			
			pageRole = item.name();                 // "ADMIN"
			pageUrl = "/" + pageRole.toLowerCase(); // "/admin"
			pageUrlWildcard = pageUrl + "/**";      // "/admin/**"
			
			http.authorizeRequests().antMatchers(pageUrl, pageUrlWildcard).hasAuthority(pageRole);

		}
		
		// ... ... ... ...
	}
```

#### Render Menu Items Accordingly (in Master Template)
```
<th:block th:each="item : ${T(MyPackage.PageRoleEnum).values()}">

	<li th:if="${#authorization.expression('hasAuthority(''' + item + ''')')}">
	
		<a th:href="@{'/' + ${#strings.toLowerCase(item)} }" >
		
			<span style="margin-left: 90px;">[[${#strings.capitalize(#strings.toLowerCase(item))}]]</span>
			
		</a>
		
	</li>

</th:block>
```
See: [Load Fragments Dynamically](https://github.com/hovermind/thymeleaf-cheat-sheet/blob/master/dynamic-fragment-name-param.md)

