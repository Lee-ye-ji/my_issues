# Error: Cannot find module 'C:\Users\YEJI\git\yebling-frontend\.next\prerender-manifest.json'

![image](https://user-images.githubusercontent.com/59958929/164447942-d503360d-96af-42a8-91ec-1c0b3fe17cbc.png)

node_modules에 패키지들을 찾지 못하겠다고 나는 오류?!

next 프레임워크의 index.js의 페이지에서 변경 후 로컬 image를 불러온 결과 났던 오류다!

음... `yarn build`시에도 에러가 발생해서 해당 문제에 대해 읽어봤더니... It's my fault...
```
[   =] info  - Generating static pages (2/3)Error
    at l (C:\Users\YEJI\git\yebling-frontend\node_modules\react-router\umd\react-router.production.min.js:11:411)
    at Object.b [as useLocation] (C:\Users\YEJI\git\yebling-frontend\node_modules\react-router\umd\react-router.production.min.js:11:3915)
    at C:\Users\YEJI\git\yebling-frontend\node_modules\react-router-dom\umd\react-router-dom.production.min.js:11:1257
    at Hc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:64:191)
    at Kc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:69:169)
    at Z (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:71:89)
    at Lc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:73:98)
    at Kc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:67:131)
    at Z (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:71:89)
    at Lc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:73:98)
Error occurred prerendering page "/". Read more: https://nextjs.org/docs/messages/prerender-error
Error
    at l (C:\Users\YEJI\git\yebling-frontend\node_modules\react-router\umd\react-router.production.min.js:11:411)
    at Object.b [as useLocation] (C:\Users\YEJI\git\yebling-frontend\node_modules\react-router\umd\react-router.production.min.js:11:3915)
    at C:\Users\YEJI\git\yebling-frontend\node_modules\react-router-dom\umd\react-router-dom.production.min.js:11:1257
    at Hc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:64:191)
    at Kc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:69:169)
    at Z (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:71:89)
    at Lc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:73:98)
    at Kc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:67:131)
    at Z (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:71:89)
    at Lc (C:\Users\YEJI\git\yebling-frontend\node_modules\react-dom\cjs\react-dom-server.browser.production.min.js:73:98)
```
해당 오류를 자세히 보면 react-router-dom이 보인다...

react에서는 react-router-dom을 이용하여 페이지를 라우팅할 수 있지만
next에서는 next/link로 라우팅을 해주어야 한다!!!

# Generating static pages (2/3)TypeError: Cannot destructure property 'auth' of 'urlObj' as it is undefined.


https://github.com/wpengine/faustjs/issues/361
