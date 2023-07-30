Next.js 기초 복습하기
1. css 적용법 -> 
styles폴더를 만든 후, Home.module.css 파일을 생성. 그 안에 원하는 css를 만들고 index.js에 적용
전체에 적용하려면 css 파일을 만들고, 그 파일을 _app.js에서 import 

일부에 적용하는 방법
// index.js
```javascript
import { Inter } from 'next/font/google'
import styles from '../styles/Home.module.css'
const inter = Inter({ subsets: ['latin'] })
export default function Home() {
  return (
    <>
    // 스타일을 적용할 땐 아래처럼
      <div className={styles.title}>hello</div>
    </>
  )
}
```

전체에 적용하는 방법
// _app.js
```javascript
import '../styles/global.css'

export default function App({ Component, pageProps }) {
  return <Component {...pageProps} />
}

```

2. 파일 시스템 기반 라우팅
라우팅이란 어떤 주소에 어떤 페이지를 보여줄지 정하는 것
파일 시스템 기반 라우팅이란 파일의 경로가 주소에 매칭되는 라우팅 방식
dynamic routing -> 여러 주소를 하나의 컴포넌트에서 처리하는 것 ex)[productId.js] -> 파일 이름을 마치 변수처럼 사용, 폴더에도 적용 가능

