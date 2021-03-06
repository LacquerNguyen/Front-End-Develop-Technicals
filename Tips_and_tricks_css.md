#### 1. CSS multiline text with ellipsis
---
**Reference :**

- [http://hackingui.com/front-end/a-pure-css-solution-for-multiline-text-truncation/](http://hackingui.com/front-end/a-pure-css-solution-for-multiline-text-truncation/)

- [https://css-tricks.com/line-clampin/](https://css-tricks.com/line-clampin/)

- [http://codepen.io/martinwolf/pen/qlFdp](http://codepen.io/martinwolf/pen/qlFdp)

**HTML :**

```html
<h2>Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et.</h2>
```

**CSS :**

```javascript
h2 {
  display: block;
  /* Fallback for non-webkit */
  display: -webkit-box;
  max-width: 400px;
  height: 109.2px;
  /* Fallback for non-webkit */
  margin: 0 auto;
  font-size: 26px;
  line-height: 1.4;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
```

#### 2. Thuộc tính css3 mới: 

#### 2. 1 CSS background-blend-mode Property

```javascript
div { 
    width: 200px;
    height: 200px;
    background-size: 200px 200px;
    background-repeat:no-repeat;
    background-image: linear-gradient(to right, black 0%, white 100%), url('w3css.gif');
    background-blend-mode: color-dodge;
}
```

##### CSS Syntax

```javascript
background-blend-mode: normal|multiply|screen|overlay|darken|lighten|color-dodge|saturation|color|luminosity;
```

#### 2. 2. object-fit

```html
<div class="image">
  <p>object-fit: cover</p>
  <img class="object-fit_cover" src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/14179/image.png">
</div>
```
##### CSS Syntax

```javascript
object-fit: | contain | cover | none | scale-down
```

#### 2. 3. object-position

```javascript

```
#### 2. 4. image-orientation

```javascript

```
#### 2.5. image-rendering

```javascript

```
#### 2.6. image-resolution

```javascript

```

#### 3. width fit-content

```javascript 
.center ul{
    width: -moz-fit-content;
    width: -webkit-fit-content;
    width: fit-content;
    margin: auto;   
} 
```

#### 4. ```-webkit-overflow-scrolling``` Khi style ```scroll``` cho một phần tử với ```overflow: auto``` thì nên để giá trị này vào:
- Thuộc tính CSS ```-webkit-overflow-scrolling``` kiểm soát xem thiết bị cảm ứng có sử dụng cuộn dựa trên động lượng cho một phần tử đã cho hay không..

```javascript 
.table-responsive {
  display: block;
  width: 100%;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  -ms-overflow-style: -ms-autohiding-scrollbar;
}
} 
```

#### 5 Flexbox Techniques You Need to Know About

#### 1. Mobile
---

>**1. Nếu làm Responsive cho Mobile thì nên set các thuộc tính dưới đây:**

html{
    -webkit-text-size-adjust: 100%;
      -ms-text-size-adjust: 100%;
}
* {
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    -webkit-tap-highlight-color: transparent;
}

>**1. Nếu làm Popop up cho Mobile, thì nên set thuộc tính này trong vùng scroll**
2. 
.modal{
  -webkit-overflow-scrolling: touch;
}

