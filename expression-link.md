## `@{...}`
* `{...}` : URL or String (Literal String, Expression)
* constructs relative url

**Server:** `localhost:8080`   
**Synatx:** `<a th:href="@{/foo}" /></a>`   
**Link (generated):** `localhost:8080/foo`   

**Server:** `localhost:8080/myapp`   
**Synatx:** `<a th:href="@{/foo}" /></a>`   
**Link (generated):** `localhost:8080/myapp/foo`   

## Constructing URL

**Literal Substition (preferred)**
```
<link th:href="@{|/foo/${bar}.css|}" rel="stylesheet" />
```

**String Concatenation**
```
<link th:href="@{'/foo/' + ${bar} + '.css'}" rel="stylesheet" />
```
