# About

Link to the comments on the post.


## Usage

```html
<b:loop values='data:posts' var='post'>
  [snippet]
</b:loop>
```


## Snippet

### Default

```html
<b:if cond='data:post.allowComments'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <a b:whitespace='remove' class='comments-link-class-name' expr:href='data:post.commentsUrl' expr:title='data:messages.comments'>
      <b:if cond='data:post.commentSource != 1'>
        <b:message name='messages.numberOfComments'>
          <b:param expr:value='data:post.numberOfComments' name='numComments'/>
        </b:message>
      <b:else/><!-- fallback -->
        <data:messages.comments/>
      </b:if>
    </a>
  <!-- /wrapper (if needed) --></div>
</b:if>
```
