## Getting template title (content title) in layout
Before (`layout` object of Thymeleaf context)
```
// 1.3.0
layout.resultingTitle

// 2.1.0
layout.contentTitle
layout.layoutTitle
```
**From version 3: [the special 'layout' object from the Thymeleaf context is removed](https://github.com/ultraq/thymeleaf-layout-dialect/issues/147)**    

**Use [fragment expression](https://github.com/thymeleaf/thymeleaf/issues/451)**
```
// layout.html

... ... ...

<body>

  <h1>[[~{ this :: title/text() }]]</h1>
  
</body>

... ... ...
```
`~{ this :: title/text() }` : get the `layout` title text (FYI, `layout` title is replaced by `template` title, so  `title/text()` is template title text)


See [title pattern](https://ultraq.github.io/thymeleaf-layout-dialect/Examples.html#configuring-your-title)
