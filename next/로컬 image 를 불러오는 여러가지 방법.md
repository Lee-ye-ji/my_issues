# 1. next.config.js파일을 추가한다.
```js
const withImages = require('next-images');
module.exports = withImages();
```

next.config.js 파일을 가장 최상위 루트에 생성하여 다음과 같은 코드를 추가한다.
next-images를 install 해주지 않았다면, 우선 설치하자~ 

이걸 추가하면 이제 로컬에서 이미지 파일을 import로 불러올 수도 있고, require 로 불러올 수도 있다.

# 2. import 로 불러오기
```js
import ExImage from '../public/img/ExImage.jpg';
```
불러오고자 하는 이미지 파일을 이렇게 불러온다
```js
<img src={ExImage} alt='이미지 테스트' />
``` 
그리고 src 안에 이렇게 import 해준 걸 넣어주면 끝!

# 3. require 로 불러오기
```js
<img src={require('../public/img/ExImage.jpg')} />
```

하지만 이 경우에도 src 경로에 오류가 난다면!
파일의 구조는 다음과 같다!
```
📁public
 ㄴ 📁img

      ㄴ 어쩌구이미지.jpg...
```

```js
<img height={200} src='/img/ExImage.jpg' />
```


https://haerim95.tistory.com/35
