# About

Link to the full post.


## Usage

```html
<b:loop values='data:posts' var='post'>
  [snippet]
</b:loop>
```


## Snippet

### Default

```html
<b:if cond='data:post.hasJumpLink'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name' expr:id='"More_" + data:widget.instanceId + "_" + data:post.id'>
    <a b:whitespace='remove' class='more-link-class-name' expr:href='fragment(data:post.url, "more")' role='button'>
      <b:attr expr:value='data:post.title ? data:post.title : ""' name='title'/>
      <data:blog.jumpLinkMessage/>
    </a>
  <!-- /wrapper (if needed) --></div>
<b:else/>
  <b:if cond='data:post.snippets'>
    <!-- wrapper (if needed) --><div class='wrapper-class-name' expr:id='"More_" + data:widget.instanceId + "_" + data:post.id'>
      <a b:whitespace='remove' class='more-link-class-name' expr:href='data:post.url' role='button'>
        <b:attr expr:value='data:post.title ? data:post.title : ""' name='title'/>
        <data:messages.keepReading/>
      </a>
    <!-- /wrapper (if needed) --></div>
  </b:if>
</b:if>
```
