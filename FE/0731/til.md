# TIL

## React

### Node.js 설치

- 버전 확인

```bash
$ node -v
$ npm -v // npm은 자동 설치
```

### React 프로젝트 생성

```bash
$ npx create-react-app [프로젝트이름] (--template cra-template-pwa-typescript)
// pwa 설치 시 괄호 안 템플릿까지 작성
// javascript로 진행 시 typescript 제외

// 버전 충돌 또는 에러가 날 경우
$ cd [프로젝트이름]

//리액트 버전 18로 다운그레이드
$ npm uninstall react react-dom
$ npm install react@18 react-dom@18

// 호횐되는 타입 버전 맞춰서 설치
$ npm install @types/react@18 @types/react-dom@18

$ npm install --save-dev @types/node
$ npm install --save-dev @testing-library/react @testing-library/jest-dom @testing-library/user-event @types/jest

$ npm install web-vitals@2.1.4
```

- 기본 설치 패키지
  - `Babel` : 코드를 구형 브라우저에서 실행하도록 변환해주는 도구 (jsx → js)
  - `ESLint` : 스크립트 코드의 문법 오류나 스타일 문제를 분석해서 알려주는 툴
    - naming convension, 미사용 변수, 오타 감지
