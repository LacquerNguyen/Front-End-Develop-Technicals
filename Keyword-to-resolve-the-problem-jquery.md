# I. Keyword to resolve the problem JQuery

1. [Scaled/Proportional Content with CSS and JavaScript](https://css-tricks.com/scaled-proportional-blocks-with-css-and-javascript/)

>**JS**
```javascript
var $el = $("#very-specific-design");
var elHeight = $el.outerHeight();
var elWidth = $el.outerWidth();
var $wrapper = $("#scaleable-wrapper");
$wrapper.resizable({  
  resize: doResize
});
function doResize(event, ui) {    
  var scale, origin;      
  scale = Math.min(ui.size.width / elWidth, ui.size.height / elHeight  );    
  $el.css({transform: "translate(-50%, -50%) " + "scale(" + scale + ")"  }); 
}
var starterData = {   
  size: {    
    width: $wrapper.width(),    
    height: $wrapper.height()  
  }
}
doResize(null, starterData);
```
>**HTML**
```javascript
<div class="scaleable-wrapper" id="scaleable-wrapper">
  <div class="very-specific-design" id="very-specific-design">
    <h1>I am designed just so.</h1>
    <p>My design is intentional. I want to be scaled in such a way that scales the design. No reflows or anything, just straight up scaling. Kinda like SVG.</p>
    <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/3/skull-and-crossbones.svg" alt="" />
    <p class="bigred"> ✖ ✖ ✖ </p>
  </div>
</div>
```
>**CSS**
```javascript
body {
  background: #ccc;
  padding: 20px;
}
.very-specific-design {
  width: 600px;
  height: 400px;
  padding: 50px;
  text-align: center;
  background: white;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  transform-origin: center center;
}
.scaleable-wrapper {
  padding: 20px;
  resize: both;
  position: relative;
  background: #666;
  height: 400px;
}
.ui-resizable-se {
  width: 10px;
  height: 10px;
  background: orange;
  position: absolute;
  bottom: 0;
  right: 0;
}
.bigred {
  color: red;
  font-size: 5rem;
}
```

1. [how to scale width content with window jquery]()


