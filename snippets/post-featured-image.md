# About

The featured image for the post.


## Usage

```html
<b:loop values='data:posts' var='post'>
  [snippet]
</b:loop>
```

##### Options

- `512` - size
- `16:9` - aspect ratio
- `512x288`
  - width = size, height = (size * ratio height) / ratio width
  - width = 512, height = (512 * 9) / 16
- `[200,400,800,1200,1600]` - srcset attribute
- `100vw` - sizes attribute


## Snippet

### Default

```html
<b:if cond='data:post.featuredImage'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    <b:else/>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    </b:if>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

### Fallback images

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    <b:else/>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    </b:if>
  <b:else/><!-- fallback -->
    <img b:whitespace='remove'>
      <b:class name='img-class-name no-img-class-name'/>
      <b:attr name='src' value='https://placehold.it/512x288/777/eee?text=No+Image'/>
      <b:attr expr:value='data:messages.image' name='alt'/>
    </img>
  </b:if>
<!-- /wrapper (if needed) --></div>
```

### Responsive images

```html
<b:if cond='data:post.featuredImage'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    <b:else/>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], "16:9") : data:post.featuredImage' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    </b:if>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

##### + Fallback images

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    <b:else/>
      <img b:whitespace='remove'>
        <b:class name='img-class-name'/>
        <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
        <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], "16:9") : data:post.featuredImage' name='srcset'/>
        <!-- sizes --><b:attr name='sizes' value='100vw'/>
        <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
      </img>
    </b:if>
  <b:else/><!-- fallback -->
    <img b:whitespace='remove'>
      <b:class name='img-class-name no-img-class-name'/>
      <b:attr name='src' value='https://placehold.it/512x288/777/eee?text=No+Image'/>
      <b:attr expr:value='data:messages.image' name='alt'/>
    </img>
  </b:if>
<!-- /wrapper (if needed) --></div>
```

### Anchors

```html
<b:if cond='data:post.featuredImage'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    </b:if>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

##### + Fallback images

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    </b:if>
  <b:else/><!-- fallback -->
    <a expr:href='data:post.link ? data:post.link : data:post.url'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name no-img-class-name'/>
        <b:attr name='src' value='https://placehold.it/512x288/777/eee?text=No+Image'/>
        <b:attr expr:value='data:messages.image' name='alt'/>
      </img>
    </a>
  </b:if>
<!-- /wrapper (if needed) --></div>
```

##### + Responsive images

```html
<b:if cond='data:post.featuredImage'>
  <!-- wrapper (if needed) --><div class='wrapper-class-name'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], "16:9") : data:post.featuredImage' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    </b:if>
  <!-- /wrapper (if needed) --></div>
</b:if>
```

##### + Responsive images + Fallback images

```html
<!-- wrapper (if needed) --><div class='wrapper-class-name'>
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, [200,400,800,1200,1600], "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    <b:else/>
      <a expr:href='data:post.link ? data:post.link : data:post.url'>
        <img b:whitespace='remove'>
          <b:class name='img-class-name'/>
          <b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage' name='src'/>
          <!-- srcset --><b:attr expr:value='data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, [200,400,800,1200,1600], "16:9") : data:post.featuredImage' name='srcset'/>
          <!-- sizes --><b:attr name='sizes' value='100vw'/>
          <b:attr expr:value='data:post.title ? data:post.title : data:messages.image' name='alt'/>
        </img>
      </a>
    </b:if>
  <b:else/><!-- fallback -->
    <a expr:href='data:post.link ? data:post.link : data:post.url'>
      <img b:whitespace='remove'>
        <b:class name='img-class-name no-img-class-name'/>
        <b:attr name='src' value='https://placehold.it/512x288/777/eee?text=No+Image'/>
        <b:attr expr:value='data:messages.image' name='alt'/>
      </img>
    </a>
  </b:if>
<!-- /wrapper (if needed) --></div>
```

### CSS background-image

```html
<b:if cond='data:post.featuredImage'>
  <div class='target-class-name'><!-- target -->
    <b:if cond='data:post.featuredImage.isYoutube'>
      <b:attr expr:value='"background-image: url(" + (data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl) + ");"' name='style'/>
    <b:else/>
      <b:attr expr:value='"background-image: url(" + (data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage) + ");"' name='style'/>
    </b:if>
  </div><!-- /target -->
</b:if>
```

##### + Fallback images

```html
<div class='target-class-name'><!-- target -->
  <b:if cond='data:post.featuredImage'>
    <b:if cond='data:post.featuredImage.isYoutube'>
      <b:attr expr:value='"background-image: url(" + (data:post.featuredImage.youtubeMaxResDefaultUrl.isResizable ? resizeImage(data:post.featuredImage.youtubeMaxResDefaultUrl, 512, "16:9") : data:post.featuredImage.youtubeMaxResDefaultUrl) + ");"' name='style'/>
    <b:else/>
      <b:attr expr:value='"background-image: url(" + (data:post.featuredImage.isResizable ? resizeImage(data:post.featuredImage, 512, "16:9") : data:post.featuredImage) + ");"' name='style'/>
    </b:if>
  <b:else/><!-- fallback -->
    <b:class name='target-class-name-no-image'/>
    <b:attr name='style' value='background-image: url(https://placehold.it/512x288/777/eee?text=No+Image);'/>
  </b:if>
</div><!-- /target -->
```
