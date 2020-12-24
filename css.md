# CSS Tips
## Handling Long Words and URLs (Forcing Breaks, Hyphenation, Ellipsis, etc)
`word-break: break-word;`

## Vertically align text next to an image?
```html
<div>
  <img style="vertical-align:middle" src="http://lorempixel.com/60/60/">
  <span style="vertical-align:middle">Perfectly centered</span>
</div>
```


## Center a Div Horizontally with Flexbox
```html
<div class="container">
  <div class="child"></div>
</div>
```
```css
.container {
  display: flex;
  justify-content: center;
}
```
