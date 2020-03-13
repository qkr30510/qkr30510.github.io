---
title: '개츠비 블로그 오류 in 윈도우'
date: 2020-3-6 16:21:13
category: 'git blog'
draft: false
---

앞서 얘기했던 것처럼 나는 이 블로그를 만들면서 몇가지의 오류에 직면 하였는데,<br> 
그 오류들은 스스로 없어지기도 했었고 우여곡절 끝에 해결하기도 하였다.<br>
오류는 크게 3가지정도로 나눌수 있을꺼 같다.

<br>

###  1. 개츠비 cil 설치 실패

처음부터 날 힘들게 했던 오류 였다.<br>
스타터를 사용했던 나는.. 왜 오류나는지 이유조차 몰랐었는데.. <br>
다행히 똑똑한 지인분이 해결해 주셨다.ㅜㅜ<br>
비쥬얼스튜디오 초기세팅을 다시 하는걸로 문제 해결하였다.<br>
[해당url 참고](https://www.gatsbyjs.org/docs/gatsby-on-windows/)

<br>


###  2. npm 오류

* ## npm not install 

    #### 1. package.lock.json 삭제
    #### 2. node_modules 삭제
    #### 3. node 재 설치 

    혹시 이래도 안된다면, 컴퓨터를 재 부팅 하길 바란다. 
    만약, 이 과정에서 **권한이 없어 ~~ 실행 할 수 없습니다.** 라는 말이 나오면 터미널을 관리자 권한으로 실행하여 하면 해결된다.

* ## can not find module 'sharp'

    해당 에러도 위의 에러와 마찬가지로 해결하면 된다.

    #### 1. package.lock.json 삭제
    #### 2. node_modules 삭제
    #### 3. node 재 설치 

<br>

###  3. GraphQL query 오류

솔직히 말하자면, 난 아직 이 오류를 해결하지 못했다.<br>
맨 처음 로컬 호스트 오류로 접속 했을때, 해당 오류가 떠서 ```Have the same issue. Deleting fragments.js - helped.``` 조언에 따라 
해당 파일을 지웠고, 로컬 에서는 정상적으로 호출이 되어 문제없이 해결 된 줄 알았다.



![로컬호스트화면에 뜬 오류 화면](/images/third-blog/localhost.png)
<pre style="text-align:right;font-style:italic">(로컬호스트화면에 뜬 오류 화면)</pre>

하지만, 이것은 내 착각이였다.
깃에 푸시를 하고 netlift를 확인하니 오류가 떠있었고 오류의 내용은 로컬호스트에 있었던 내용과 동일한 ```Unknown type "ContentfulFluid"``` <br>그 외의 다른 오류도 있다.) 가 있었다. 

```
7:08:36 PM: Build ready to start
7:08:38 PM: build-image version: 2dbd444fcdce00cf06325060a8238d5ae3e86774
7:08:38 PM: build-image tag: v3.3.7
7:08:38 PM: buildbot version: 11918e084194721d200458438c92ff8180b3b56c
7:08:39 PM: Fetching cached dependencies
7:08:39 PM: Starting to download cache of 254.9KB
7:08:39 PM: Finished downloading cache in 129.423228ms
7:08:39 PM: Starting to extract cache
7:08:39 PM: Failed to fetch cache, continuing with build
7:08:39 PM: Starting to prepare the repo for build
7:08:39 PM: No cached dependencies found. Cloning fresh repo
7:08:39 PM: git clone https://github.com/qkr30510/qkr30510.github.io
7:08:40 PM: Preparing Git Reference refs/heads/master
7:08:41 PM: Starting build script
7:08:41 PM: Installing dependencies
7:08:42 PM: v10.19.0 is already installed.
7:08:43 PM: Now using node v10.19.0 (npm v6.13.4)
7:08:43 PM: Attempting ruby version 2.6.2, read from environment
7:08:45 PM: Using ruby version 2.6.2
7:08:45 PM: Using PHP version 5.6
7:08:45 PM: Started restoring cached node modules
7:08:45 PM: Finished restoring cached node modules
7:08:45 PM: Installing NPM modules using NPM version 6.13.4
7:09:32 PM: > sharp@0.23.4 install /opt/build/repo/node_modules/sharp
7:09:32 PM: > (node install/libvips && node install/dll-copy && prebuild-install) || (node-gyp rebuild && node install/dll-copy)
7:09:33 PM: info
7:09:33 PM: sharp
7:09:33 PM:  Downloading https://github.com/lovell/sharp-libvips/releases/download/v8.8.1/libvips-8.8.1-linux-x64.tar.gz
7:09:35 PM: > node-sass@4.13.1 install /opt/build/repo/node_modules/node-sass
7:09:35 PM: > node scripts/install.js
7:09:36 PM: Downloading binary from https://github.com/sass/node-sass/releases/download/v4.13.1/linux-x64-64_binding.node
7:09:36 PM: Download complete
7:09:36 PM: Binary saved to /opt/build/repo/node_modules/node-sass/vendor/linux-x64-64/binding.node
7:09:36 PM: Caching binary to /opt/buildhome/.npm/node-sass/4.13.1/linux-x64-64_binding.node
7:09:37 PM: > core-js@2.6.11 postinstall /opt/build/repo/node_modules/core-js
7:09:37 PM: > node -e "try{require('./postinstall')}catch(e){}"
7:09:37 PM: Thank you for using core-js ( https://github.com/zloirock/core-js ) for polyfilling JavaScript standard library!
7:09:37 PM: The project needs your help! Please consider supporting of core-js on Open Collective or Patreon: 
7:09:37 PM: > https://opencollective.com/core-js 
7:09:37 PM: > https://www.patreon.com/zloirock 
7:09:37 PM: Also, the author of core-js ( https://github.com/zloirock ) is looking for a good job -)
7:09:37 PM: > gatsby-telemetry@1.1.49 postinstall /opt/build/repo/node_modules/gatsby-telemetry
7:09:37 PM: > node src/postinstall.js || true
7:09:37 PM: > cwebp-bin@5.1.0 postinstall /opt/build/repo/node_modules/cwebp-bin
7:09:37 PM: > node lib/install.js
7:09:38 PM:   ✔ cwebp pre-build test passed successfully
7:09:38 PM: > mozjpeg@6.0.1 postinstall /opt/build/repo/node_modules/mozjpeg
7:09:38 PM: > node lib/install.js
7:09:39 PM:   ✔ mozjpeg pre-build test passed successfully
7:09:39 PM: > pngquant-bin@5.0.2 postinstall /opt/build/repo/node_modules/pngquant-bin
7:09:39 PM: > node lib/install.js
7:09:39 PM:   ✔ pngquant pre-build test passed successfully
7:09:39 PM: > gatsby-cli@2.9.0 postinstall /opt/build/repo/node_modules/gatsby/node_modules/gatsby-cli
7:09:39 PM: > node scripts/postinstall.js
7:09:39 PM: > gatsby@2.19.23 postinstall /opt/build/repo/node_modules/gatsby
7:09:39 PM: > node scripts/postinstall.js
7:09:40 PM: > node-sass@4.13.1 postinstall /opt/build/repo/node_modules/node-sass
7:09:40 PM: > node scripts/build.js
7:09:40 PM: Binary found at /opt/build/repo/node_modules/node-sass/vendor/linux-x64-64/binding.node
7:09:40 PM: Testing binary
7:09:40 PM: Binary is fine
7:09:44 PM: npm
7:09:44 PM: WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 (node_modules/webpack-dev-server/node_modules/fsevents):
7:09:44 PM: npm WARN
7:09:44 PM: notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.11: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
7:09:44 PM: npm
7:09:44 PM: WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 (node_modules/watchpack/node_modules/fsevents):
7:09:44 PM: npm WARN
7:09:44 PM: notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.11: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
7:09:44 PM: npm
7:09:44 PM:  WARN optional
7:09:44 PM:  SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.11 (node_modules/babel-plugin-add-module-exports/node_modules/fsevents):
7:09:44 PM: npm
7:09:44 PM: WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.11: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
7:09:44 PM: npm WARN
7:09:44 PM: optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.1.2 (node_modules/chokidar/node_modules/fsevents):
7:09:44 PM: npm WARN
7:09:44 PM:  notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.1.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
7:09:44 PM: added 2353 packages from 1008 contributors and audited 33838 packages in 57.657s
7:09:47 PM: 106 packages are looking for funding
7:09:47 PM:   run `npm fund` for details
7:09:47 PM: found 31 vulnerabilities (3 moderate, 28 high)
7:09:47 PM:   run `npm audit fix` to fix them, or `npm audit` for details
7:09:47 PM: NPM modules installed
7:09:47 PM: Started restoring cached go cache
7:09:47 PM: Finished restoring cached go cache
7:09:47 PM: unset GOOS;
7:09:47 PM: unset GOARCH;
7:09:47 PM: export GOROOT='/opt/buildhome/.gimme/versions/go1.12.linux.amd64';
7:09:47 PM: export PATH="/opt/buildhome/.gimme/versions/go1.12.linux.amd64/bin:${PATH}";
7:09:47 PM: go version >&2;
7:09:47 PM: export GIMME_ENV='/opt/buildhome/.gimme/env/go1.12.linux.amd64.env';
7:09:47 PM: go version go1.12 linux/amd64
7:09:47 PM: Installing missing commands
7:09:47 PM: Verify run directory
7:09:47 PM: Executing user command: gatsby build
7:09:50 PM: success open and validate gatsby-configs - 0.098s
7:09:51 PM: success load plugins - 1.372s
7:09:52 PM: warning The Google Analytics plugin requires a tracking ID. Did you mean to add it?
7:09:52 PM: success onPreInit - 0.012s
7:09:52 PM: success delete html and css files from previous builds - 0.016s
7:09:52 PM: success initialize cache - 0.011s
7:09:52 PM: success copy gatsby files - 0.057s
7:09:52 PM: warning gatsby-plugin-feed was initialized in gatsby-config.js without a feeds option.
7:09:52 PM: This means that the plugin will use the internal RSS feed creation, which may not match your use case.
7:09:52 PM: This behavior will be removed in the next major release of gatsby-plugin-feed.
7:09:52 PM: For more info, check out: https://gatsby.dev/adding-rss-feed
7:09:52 PM: success onPreBootstrap - 0.012s
7:09:52 PM: success createSchemaCustomization - 0.134s
7:09:52 PM: success source and transform nodes - 0.277s
7:09:52 PM: success building schema - 0.456s
7:09:53 PM: success createPages - 0.071s
7:09:53 PM: success createPagesStatefully - 0.113s
7:09:53 PM: success onPreExtractQueries - 0.000s
7:09:53 PM: success update schema - 0.038s
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFixed".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFixed".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFixed".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFixed".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFixed".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFluid".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFluid".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFluid".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFluid".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulFluid".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulResolutions". Did you mean "ImageSharpResolutions"?
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulResolutions". Did you mean "ImageSharpResolutions"?
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulResolutions". Did you mean "ImageSharpResolutions"?
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulResolutions". Did you mean "ImageSharpResolutions"?
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulResolutions". Did you mean "ImageSharpResolutions"?
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulSizes".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulSizes".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulSizes".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulSizes".
7:09:53 PM: error There was an error in your GraphQL query:
7:09:53 PM: Unknown type "ContentfulSizes".
7:09:53 PM: failed extract queries from components - 0.653s
7:09:53 PM: Skipping functions preparation step: no functions directory set
7:09:53 PM: Caching artifacts
7:09:53 PM: Started saving node modules
7:09:53 PM: Finished saving node modules
7:09:53 PM: Started saving pip cache
7:09:54 PM: Finished saving pip cache
7:09:54 PM: Started saving emacs cask dependencies
7:09:54 PM: Finished saving emacs cask dependencies
7:09:54 PM: Started saving maven dependencies
7:09:54 PM: Finished saving maven dependencies
7:09:54 PM: Started saving boot dependencies
7:09:54 PM: Finished saving boot dependencies
7:09:54 PM: Started saving go dependencies
7:09:54 PM: Finished saving go dependencies
7:09:57 PM: Error running command: Build script returned non-zero exit code: 1
7:09:57 PM: Failing build: Failed to build site
7:09:57 PM: failed during stage 'building site': Build script returned non-zero exit code: 1
7:09:57 PM: Finished processing build request in 1m18.618682669s
```
<pre style="text-align:right;font-style:italic">(netlify에 뜬 오류 화면)</pre>

흠.. 어렵다 <br>
우선 내가 찾은 바로는 ```ContentfulFixed```해당 변수?는 **contentful** 이라는 [API](https://www.contentful.com/) 이며, ```클라우드 기반의 Headless CMS 이다.``` <br> 
Gatsby 내부 GraphQL 노드로 추가해 주는 gatsby-source-contentful 플러그인이 있어서 두 개를 연결해주는거 같은데,<br> gatsby-source-contentful를 npm 으로 설치를 해주면, gatsby-configs.js에 별도로 추가를 해줘야 한다. <br>
하지만, 난 굳이 사용하고 싶지 않기 떄문에 지웠던거였고.. 아니 애초에 난 설치를 안했었는데 왜 생겼던 것일까?<br>
아무튼 그럼 캐시의 문제거나 한번 설치 되었기 때문에 GraphQL 노드에 저장되어있을꺼 같다.<br>
한번 캐시를 지워봐야겠다. 

* 캐시 지워봤는데 안됨 ㅠㅠ 

## 아휴 드디어 해결되었다!!!.

의외인곳에서 해결되었는데, package.json에 gatsby-source-contentful 버전이 기록되어있어서 그런거였다 ㅜㅜ.<br>
그곳에 적혀져있는건 알았는데.. 그곳에 써져있어서 안되는건지는 몰랐다...<br>
와.. 진짜.. <br>
덕분에 여러가지 배우긴 했다만 너무 허탈하네.. 이제 누군가가 정말 볼수있으니 외적인것 먼저 수정부터 하고 react도 공부하면서 병행해야겠다.


