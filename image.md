# Best practices for img tag

- Add width and height attributes - intrinsic image properties, better to use software with automatic calculation.
  This will remove `jank` - layout jumping.
- For adaptive design add CSS style use `img {width: 100%, height: auto; }`.

## Links

https://github.com/WICG/intrinsicsize-attribute/issues/16

https://www.youtube.com/watch?v=4-d_SoCHeWE

## Code 

HTML:
```
<img src="dog.jpg" width="400" height="300">
```

CSS:
```
img, video {
    width: 100%;
    height: auto;
    aspect-ratio: attr(width) / attr(height); <!-- for browsers older than Blink 71 -->
} 
```

## Alternative image

Browsers have different image type support (PNG, JPEG, WebP, SVG).
Use `<picture>` tag for modern and older formats. Picture can be used with the adaptive design above only if the images ratio is the same for all of them.

See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture
