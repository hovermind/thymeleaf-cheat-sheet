* Spring Expression Language (spEL)
* executed on the context variables (also called model attributes in Spring jargon)
```
<p th:text=${session.user.name}></p>
```

## Model Attribute
`FooController.java`
```
public class FooController{

  GetMapping("/baz")
  public class showView(Model ctxModel){
  
    ctxModel.addAttribute("x", 10);
    ctxModel.addAttribute("bar", object);
    
    return "baz";
  }
}
```

Using model attribute 'x' in template
```
<p th:text="${x}"></p>

// inlining
<p>[[ ${ x } ]]</p>
```

Using property of bar object
```
<p th:text="${bar.id}"></p>
```

## Using Property of Exposed Object
```
<div th:object="${foo}">
  <p th:text="${id}"></p>
</div>
```

## Getting Thymeleaf Variable
```
<div th:with="id=${foo.id}">
  <p th:text="${id}"></p>
</div>
```
