#### Inlining expression in Thymeleaf: `[[ ]]` 
Expressions between `[[...]]` is considered expression inlining in Thymeleaf, and in them you can use any kind of expression that would also be valid in a th:text attribute.
   
In order for inlining to work, we must activate it by using the `th:inline` attribute, which has three possible values or modes 
* text
* javascript
* none

## Text inlining
```
<p th:inline="text"> Hello, [[${session.user.name}]]! </p>

// or
<body th:inline="text">

   ...

   <p> Hello, [[${session.user.name}]]! </p>

   ...

</body>
```
## Script inlining
```
<script th:inline="javascript">
/*<![CDATA[*/
    ...

    var username = /*[[${session.user.name}]]*/ 'Sebastian';

    ...
/*]]>*/
</script>
```
* Being a javascript comment (/*...*/), our expression will be ignored when displaying the page statically in a browser.
* The code after the inline expression ('Sebastian') will be executed when displaying the page statically.
* Thymeleaf will execute the expression and insert the result, but it will also remove all the code in the line after the inline expression itself (the part that is executed when displayed statically).

Details [thymeleaf text inlining](https://www.thymeleaf.org/doc/tutorials/2.1/usingthymeleaf.html#inlining)
