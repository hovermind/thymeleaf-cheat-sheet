## Dissecting Thymeleaf Syntax
**Synatx: `<p th:text="${#session.getAttribute('name') + 'San'}"></p>`**

#### `th:text`
* standard dialect (Dialect == Propcessor - something that has special meaning to thymeleaf & executes operations)
* generates plain text and set inner HTML of `</p>`

#### `${...}`
* variable expression - executes on model attribute, thymeleaf varibale (`th:with`)
```
<div th:with="id=${foo.id}">
  <p th:text="${id}"></p>
</div>
```

#### `#session.getAttribute('name')`
* expression object
* `#session` is equivalent of java `HttpSession` object
