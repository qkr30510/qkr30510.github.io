---
title: v-for 사용시 문제점
date: 2020-11-24 13:11:38
category: vue
draft: false
---

vue로 작업해야할 일들이 생겨나 vue 공부를 급하게 진행하였다.
가장 기본적인 nav를 제작하는데 v-for문에 자꾸 에러가 걸려 확인해보니 li에서 v-for를 사용할때에는 v-bind를 함께 써줘야 했다.

```vue
// 에러 난 코드
<template>
  <div class="nav">
    <ul>
      <li>로고</li>
      <li v-for="list in linklist">
        <router-link :to="list.link">{{ list.content }}</router-link>
      </li>
      <li>story</li>
      <li>contact</li>
    </ul>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  data() {
    return {
      toggle: this.enter,
      linklist: [
        { content: 'portfolio', link: '/portfolio' },
        { content: 'story', link: '/story' },
        { content: 'contact', link: '/contact' },
      ],
    }
  },
}
</script>

```

```vue
// 해결 한 코드

<template>
  <div class="nav">
    <ul>
      <li>로고</li>
      <li v-for="list in linklist" v-bind:key="list.conten">
        <router-link :to="list.link">{{ list.content }}</router-link>
      </li>
      <li>story</li>
      <li>contact</li>
    </ul>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  data() {
    return {
      toggle: this.enter,
      linklist: [
        { content: 'portfolio', link: '/portfolio' },
        { content: 'story', link: '/story' },
        { content: 'contact', link: '/contact' },
      ],
    }
  },
}
</script>
```
