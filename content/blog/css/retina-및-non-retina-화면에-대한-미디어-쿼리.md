---
title: Retina 및 Non Retina 화면에 대한 미디어 쿼리
date: 2020-12-01 18:12:58
category: css
draft: false
---

새롭게 일을 하다가 기존 작업자가 코드 작성한 걸 보고 새로 배우게 되었다.
예전에 어떤 언니와 일할때, "맥은 픽셀이 달라서 따로 이미지 3배수 해줘야해~" 하고 얘기만 듣고 이전회사에서도 적용을 못했었는데, 알고보니 미디어쿼리로 처리해줘야 하는 문제였나보다.
코드를 설명하기 전에 먼저 **Retina 및 Non Retina 화면**에 대해 설명하면 좋을 것 같다.
**_Retina_**는 고밀도 디스플레이를 뜻하며, 1px안에 더 많은 픽셀이 들어가고 화면은 더 선명하게 표현할 수 있게 되었다. 픽셀 밀도가 높을수록 픽셀 크기는 작아집니다.
1px안에 얼마나 많은 1dp가 들어가는지를 봐야한다. 이를 **밀도 독립적 픽샐(dp)**라고 한다.

```javascript
// 사용 예
@media (-webkit-min-device-pixel-ratio: 2), (min--moz-device-pixel-ratio: 2), (-o-min-device-pixel-ratio: 2/1), (min-resolution: 2dppx), (min-resolution: 192dpi) {
  .empty-data .icon-cart-empty {
    background-image: url("/res/images/icon-cart-empty@2x.png");
  }
}

@media (-webkit-c), (min--moz-device-pixel-ratio: 3), (-o-min-device-pixel-ratio: 3/1), (min-resolution: 3dppx), (-webkit-min-device-pixel-ratio: 2), (-o-min-device-pixel-ratio: 2/1), (min-resolution: 192dpi) {
  .empty-data .icon-cart-empty {
    background-image: url("/res/images/icon-cart-empty@3x.png");
  }
}
```
