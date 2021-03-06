# About

Name of the profile of the post author.


## Usage

```html
<b:loop values='data:posts' var='post'>
  [snippet]
</b:loop>
```


## Snippet

### Default

```html
<b:if cond='data:post.author'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <span class='author-class-name'><data:post.author.name/></span>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

### Fallback

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.author'>
    <span class='author-class-name'><data:post.author.name/></span>
  <b:else/><!-- fallback -->
    <span class='author-anonymous-class-name'>Anonymous</span>
  </b:if>
<!-- /wrapper (if needed) --></div>
```

### Anchors

```html
<b:if cond='data:post.author'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <b:if cond='data:post.author.profileUrl'>
      <a b:whitespace='remove' class='author-class-name' expr:href='data:post.author.profileUrl' expr:title='data:messages.visitProfile'>
        <data:post.author.name/>
      </a>
    <b:else/><!-- no profileUrl -->
      <span class='author-no-url-class-name'><data:post.author.name/></span>
    </b:if>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

##### + Fallback

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.author'>
    <b:if cond='data:post.author.profileUrl'>
      <a b:whitespace='remove' class='author-class-name' expr:href='data:post.author.profileUrl' expr:title='data:messages.visitProfile'>
        <data:post.author.name/>
      </a>
    <b:else/><!-- no profileUrl -->
      <span class='author-no-url-class-name'><data:post.author.name/></span>
    </b:if>
  <b:else/><!-- fallback -->
    <span class='author-anonymous-class-name'>Anonymous</span>
  </b:if>
<!-- /wrapper (if needed) --></div>
```
