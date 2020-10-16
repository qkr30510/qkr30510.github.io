---
title: JS를 이용해서 SlideUP SlideDown 효과주기
date: 2020-10-16 17:10:73
category: javascript
draft: false
---

제이쿼리를 사용하지 않고 순수 자바스크립트로 slideUp/slideDown를 찾아보았다.

```javascript
var minheight = 20
var maxheight = 100
var time = 1000
var timer = null
var toggled = false

window.onload = function() {
  var controller = document.getElementById('slide')
  var slider = document.getElementById('slider')
  slider.style.height = minheight + 'px' //not so imp,just for my example
  controller.onclick = function() {
    clearInterval(timer)
    var instanceheight = parseInt(slider.style.height) // Current height
    var init = new Date().getTime() //start time
    var height = (toggled = !toggled) ? maxheight : minheight //if toggled

    var disp = height - parseInt(slider.style.height)
    timer = setInterval(function() {
      var instance = new Date().getTime() - init //animating time
      if (instance <= time) {
        //0 -> time seconds
        var pos = instanceheight + Math.floor((disp * instance) / time)
        slider.style.height = pos + 'px'
      } else {
        slider.style.height = height + 'px' //safety side ^^
        clearInterval(timer)
      }
    }, 1)
  }
}
```

출처: https://stackoverflow.com/questions/3795481/javascript-slidedown-without-jquery
