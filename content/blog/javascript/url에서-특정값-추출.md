---
title: url에서 특정값 추출
date: 2020-10-14 10:10:94
category: javascript
draft: false
---

``` javascript
		function getParameterByName(name) {
			name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
			var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
				results = regex.exec(location.search);
			return results === null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
		}
		refererType = getParameterByName('rc'); // rc부분에 본인이 원하는 데이터 이름 넣으면 된다.
		console.log(refererType)
		
		// 레퍼럴 체크 
```       