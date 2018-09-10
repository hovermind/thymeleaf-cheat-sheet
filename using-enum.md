## Accessing Enum values in thymeleaf
```
<th:block th:each="item : ${T(MyPackage.MyEnum).values()}">

</th:block>
```
`T()` => `type` for `Class`, `Enum` etc
