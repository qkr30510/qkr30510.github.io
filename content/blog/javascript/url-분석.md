---
title: location을 이용한 url 분석
date: 2020-08-31 12:08:27
category: javascript
draft: false
---

일을 하다가 url에 따라 컨테츠가 보여야하는 부분이 있었다.
(루트페이지에만 컨텐츠가 나타났어야 함)

어떻게 해야되는지 몰랐었는데, 검색해보니 location으로 다양하게 현재 url이 분석이 가능하였다.

### location을 이용한 코드

```javascript

location.protocol : http: // 프로토콜 분석
location.host : example.com // 도메인
location.pathname : test/sample // 서브페이지
location.search : ?id=123&name=test // 파라미터

```

### location을 이용한 코드 활용 방법

```javascript
$(document).ready(function() {
			var nowUrl =  window.location.pathname; // 변수에 넣음
			console.log(nowUrl)
			if(nowUrl == '/') { // /슬래시가 나오길래 넣었다.
				$('#popup_cost').show();
		    }
			console.log(window.location.host, nowUrl, window.location.pathname )
}

```

### 추가적으로..

```javascript
var nowUrl = window.location.href
if (nowUrl.indexOf('makeCostbox') > -1) {
  $(window).scrollTop($('#makeCostbox').offset().top - 40)
}
```

해당방법은 해당 url에 makeCostbox가 들어가 있으면 스크롤의 위치가 top -40 으로 되게하는 스크립트다.
