---
title: input value값 변경 체크
date: 2020-09-25 16:09:69
category: javascript
draft: false
---

### 문제

1. input 4개가 주어지고 모든 input에 값이 들어가있어야함.
2. 마지막 input에 값이 들어가는게 체크가 되면 버튼이 활성화가 되어야함.

### 해결방법

```html
<div class="upload_label_box">
  <div class="upload_label_sbox">
    <p>이름</p>
    <input
      type="text"
      id="privacyName"
      class="privacyInput"
      value=""
      placeholder="이름"
    />
  </div>
  <div class="upload_label_sbox">
    <p>주민등록번호</p>
    <input
      type="text"
      id="privacyId"
      class="privacyInput"
      value=""
      placeholder="주민등록번호 13자리"
    />
  </div>
  <div class="upload_label_sbox">
    <p>은행명</p>
    <input
      type="text"
      id="privacyBank"
      class="privacyInput"
      value=""
      placeholder="은행 이름"
    />
  </div>
  <div class="upload_label_sbox">
    <p>계좌번호</p>
    <input
      type="text"
      id="privacyBankId"
      class="privacyInput"
      value=""
      placeholder="계좌번호"
    />
  </div>
</div>
<button
  type="button"
  class="iu-cell cell-29 upload_link_confirm privacy_btn"
  disabled=""
>
  등록
</button>
```

```javascript
function privacy() {
  var newValue
  // 모든 텍스트의 변경에 반응합니다.
  $('.privacyInput').on('propertychange change keyup paste input', function() {
    var privacyName = document.getElementById('privacyName').value // 이름
    var privacyId = document.getElementById('privacyId').value // 주민번호
    var privacyBank = document.getElementById('privacyBank').value // 은행
    var privacyBankId = document.getElementById('privacyBankId').value //은행계좌
    var noValue = !privacyName || !privacyId || !privacyBank || !privacyBankId

    // 현재 변경된 데이터 셋팅
    newValue = $(this).val()

    // 현재 실시간 데이터 표츌
    if (newValue === '') {
      $(this)
        .parents('.privacy_writebox')
        .find('.privacy_btn')
        .css('background', '#ccc')
      $(this)
        .parents('.privacy_writebox')
        .find('.privacy_btn')
        .attr('disabled', true)
    } else {
      if (noValue) {
        $(this)
          .parents('.privacy_writebox')
          .find('.privacy_btn')
          .attr('disabled', true)
        return
      } else {
        //alert();
        $(this)
          .parents('.privacy_writebox')
          .find('.privacy_btn')
          .css('background', '#000')
        $(this)
          .parents('.privacy_writebox')
          .find('.privacy_btn')
          .attr('disabled', false)
      }
    }
  }) //개인정보 기입 칸 누르는 값에 의해 버튼값 활성화

  $('.privacy_btn').click(function() {
    $(this)
      .parents('.privacy_writebox')
      .hide()
    $(this)
      .parents('.privacy_writebox')
      .siblings('.privacy_checkbox')
      .show()
  }) // 기입완료버튼

  $('.privacy_checkbox_prev').click(function() {
    $(this)
      .parents('.privacy_checkbox')
      .hide()
    $(this)
      .parents('.privacy_checkbox')
      .siblings('.privacy_writebox')
      .show()
  }) // 이전버튼

  $('.privacy_checkbox_next').click(function() {
    $(this)
      .parents('.privacy_checkbox')
      .hide()
    $(this)
      .parents('.privacy_checkbox')
      .siblings('.privacy_confirmbox')
      .show()
  }) // 다음버튼
} // 개인정보완료
privacy()
```
