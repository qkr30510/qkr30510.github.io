---
title: scrollTop
date: 2020-10-30 11:10:98
category: jquery
draft: false
---

스크롤 위치를 기억하고 해당 위치에 도달했을떄 이벤트를 발생해야하는 일이 종종 있다.
그때 사용하면 좋은 이벤트이다.

```javascript

	// 메인 탭에 따라 메뉴 보임 끝
	var lnb = $(".위치찾고싶은아이").offset().top;

	//console.log('lnb',lnb)
	$(window).scroll(function() {

		if($( document ).scrollTop() > lnb) {
			// 스크롤이 넘어갈때 행해질 이벤트
		} else {
			// 스크롤이 넘어가지 않을때 행해질 이벤트
		}
	});


});

```
