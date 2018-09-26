## Syntax
Fragment Expression:
```
~{ }
~{ templates/fragments/foo_fragments :: bar_section }
~{ this :: title }
```

**Using fragment in view**
```
<div th:insert="~{ }" >

</div>

<div th:replace="~{ }" >

</div>
```

## Condition in Fragment Expression
```
<div th:insert="${ #authorization.expression('hasAuthority('''A''')') } ? ~{ fragments :: A } : ~{ fragments :: B }" >

</div>
```
**For empty fragment** => `~{ }`
```
<div th:insert="${ #authorization.expression('hasAuthority('''A''')') } ? ~{ fragments :: A } : ~{ }" >

</div>
```

See:
* [thymeleaf page - layouts](https://www.thymeleaf.org/doc/articles/layouts.html)
* [baeldung - spring thymeleaf fragments](https://www.baeldung.com/spring-thymeleaf-fragments)
