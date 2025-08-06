## TIL - React

### 로컬 개발 용 데이터 베이스 설치 (json-server)

```bash
$ npm install -g json-server@0.17.0
// 버전 명시 -> @0.17.0
// 전역 설치 -> -g

// 서버 기동
// port 번호는 옵션
$ json-server --watch [db주소] [--port xxxx]

// 에러 발생 시
$ npx json-server --watch [db주소] [--port xxxx]
```

### axios 설치

```bash
$ npm install axios
```

### react-router-dom, styled-components

```bash
$ npm install react-router-dom
$ npm install styled-components
```

---

### Context

: 컴포넌트의 props를 통한 데이터 전달 (drilling의 불편함을 해소)
