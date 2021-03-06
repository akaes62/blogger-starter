# About

The share buttons for the post.


## Usage

```html
<b:loop values='data:posts' var='post'>
  [snippet]
</b:loop>
```


## Snippet

### Default

```html
<a class='share-class-name' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=twitter"' target='_blank'>
  <i aria-hidden='true' class='icon icon-twitter'/>
  Twitter
</a>
<a class='share-class-name' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=facebook"' target='_blank'>
  <i aria-hidden='true' class='icon icon-facebook'/>
  Facebook
</a>
<a class='share-class-name' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=googlePlus"' target='_blank'>
  <i aria-hidden='true' class='icon icon-gplus'/>
  Google+
</a>
<a class='share-class-name' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=pinterest"' target='_blank'>
  <i aria-hidden='true' class='icon icon-pinterest'/>
  Pinterest
</a>
<a class='share-class-name' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=email"' target='_blank'>
  <i aria-hidden='true' class='icon icon-email'/>
  Email
</a>
<a class='share-class-name' expr:onclick='"window.open(&amp;quot;https://www.blogger.com/blog-this.g?n=" + data:blog.title + ": " + (data:post.title ? data:post.title : data:messages.noTitle) + "&amp;u=" + data:post.url + "&amp;t=&amp;quot;, &amp;quot;_blank&amp;quot;, &amp;quot;directories=no, titlebar=no, toolbar=no, location=no, status=no, menubar=no, scrollbars=yes, resizable=yes, width=800, height=600&amp;quot;);"' href='javascript:void(0)'>
  <i aria-hidden='true' class='icon icon-blogger'/>
  BlogThis!
</a>
```

### Dropdown example

```html
<div class='dropdown-wrapper'>
  <a aria-expanded='false' aria-haspopup='true' b:whitespace='remove' class='dropdown-toggle' data-toggle='dropdown' expr:id='"DropdownMenuSharing_" + data:widget.instanceId + "_" + data:post.id' expr:title='data:messages.share' href='#'>
    <i aria-hidden='true' class='icon icon-share'/>
    <data:messages.share/>
  </a>
  <div class='dropdown-menu' expr:aria-labelledby='"DropdownMenuSharing_" + data:widget.instanceId + "_" + data:post.id'>
    <a class='dropdown-item' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=twitter"' target='_blank'>
      <i aria-hidden='true' class='icon icon-twitter'/>
      Twitter
    </a>
    <a class='dropdown-item' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=facebook"' target='_blank'>
      <i aria-hidden='true' class='icon icon-facebook'/>
      Facebook
    </a>
    <a class='dropdown-item' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=googlePlus"' target='_blank'>
      <i aria-hidden='true' class='icon icon-gplus'/>
      Google+
    </a>
    <a class='dropdown-item' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=pinterest"' target='_blank'>
      <i aria-hidden='true' class='icon icon-pinterest'/>
      Pinterest
    </a>
    <a class='dropdown-item' expr:href='"https://www.blogger.com/share-post.g?blogID=" + data:blog.blogId + "&amp;postID=" + data:post.id + "&amp;target=email"' target='_blank'>
      <i aria-hidden='true' class='icon icon-email'/>
      Email
    </a>
    <a class='dropdown-item' expr:onclick='"window.open(&amp;quot;https://www.blogger.com/blog-this.g?n=" + data:blog.title + ": " + (data:post.title ? data:post.title : data:messages.noTitle) + "&amp;u=" + data:post.url + "&amp;t=&amp;quot;, &amp;quot;_blank&amp;quot;, &amp;quot;directories=no, titlebar=no, toolbar=no, location=no, status=no, menubar=no, scrollbars=yes, resizable=yes, width=800, height=600&amp;quot;);"' href='javascript:void(0)'>
      <i aria-hidden='true' class='icon icon-blogger'/>
      BlogThis!
    </a>
  </div>
</div>
```
