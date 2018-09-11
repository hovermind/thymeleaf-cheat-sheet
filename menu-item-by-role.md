## `sec:authorize-url`
```
<div sec:authorize-url="/admin">
    This will only be displayed if authenticated user can call the "/admin" URL.
</div>

<div sec:authorize-url="/dba">
    This will only be displayed if authenticated user can call the "/dba" URL.
</div>

<div sec:authorize-url="/mentor">
    This will only be displayed if authenticated user can call the "/mentor" URL.
</div>
```
For specifying a specific HTTP method, do:
```
<div sec:authorize-url="POST /admin">
    This will only be displayed if authenticated user can call the "/admin" URL
    using the POST HTTP method.
</div>
```
See: [Thymeleaf - Spring Security integration](https://github.com/thymeleaf/thymeleaf-extras-springsecurity)
