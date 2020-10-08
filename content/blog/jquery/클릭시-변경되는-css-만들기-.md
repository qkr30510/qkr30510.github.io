---
title: 클릭시 변경되는 css 만들기 
date: 2020-10-08 14:10:18
category: jquery
draft: false
---

클릭될때마다 height가 늘어나야하는 jq를 만들어야하는 일이 있어 만들게 되었다. 
for문을 공부했다고 해서 for문으로 만들려고 이리저리 하다가 결국 animate를 사용하여 만들게 되었다. 

아주 간단하다. 

```javascript
$(this).siblings('.naver-proudct-wrap').animate({height:'+=725'+'px'})
```
