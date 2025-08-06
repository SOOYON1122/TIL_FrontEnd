# React - Mini Project(1)

## Directory

```
📂 mini-pjt
├─ .env
├─ db.json
├─ package-lock.json
├─ package.json
├─ 📂 public
└─ 📂 src
   ├─ 📂 api
   │  └─ axios.js
   ├─ App.css
   ├─ App.js
   ├─ App.test.js
   ├─ 📂 component
   ├─ index.css
   ├─ index.js
   ├─ logo.svg
   ├─ 📂 page
   ├─ reportWebVitals.js
   └─ setupTests.js

```

---

## .env

**반드시 접두어로 `REACT` 필요**

ex) REACT_APP_JSON_SERVER_URL=http://localhost:4000/

- 주석 처리 : `#`
- 사용 방법 : `process.env.REACT_APP_JSON_SERVER_URL`

---

## Axios

### 시작하기

```bash
$ npm install axios
```

### 사용하기

- 컴포넌트화
- directory
  - ```
    📂 src
    └─ 📂 api
       └─ axios.js
    ```

### `axios.js`

- api 호출 재사용성 🔺
- axios 인스턴스 생성
- ```js
  const api = axios.create({
    baseURL: "{호출 시 필요한 주소}",
    withCredentials: true,
  });
  ```
  - `withCredentials: true,`
    - CORS 요청 시 쿠키, 인증 헤더 등을 포함하도록 설정
    - 서버가 인증이 필요한 경우(예: 로그인 세션 유지)에 사용

### axios 인스턴스 사용

> **post**
>
> - 데이터 입력
>
> **get**
>
> - 데이터 가져올 때
>
> **put**
>
> - 데이터 수정 (리소스 전체 수정하거나, 새로 생성)
>
> **delete**
>
> - 데이터 삭제
>
> **patch**
>
> - 데이터 일부 수정

**status**

> **200**
>
> - OK
> - 데이터 조회
>
> **201**
>
> - created
> - 요청이 성공적으로 처리되어 리소스가 새로 생성될 때
> - POST 사용 시
>
> **204**
>
> - No Content
> - 요청이 성공적으로 처리되었으나 반환할 데이터가 없을 때
> - DELETE 사용 시
>
> **400**
>
> - Bad Request
> - 잘못된 요청 (파라미터 오류 등)
>
> **401**
>
> - UnAuthorized
> - 인증이 필요하거나 인증 실패
>
> **403**
>
> - Forbidden
> - 권한이 없어 접근 불가
>
> **404**
>
> - Not found
> - 요청한 리소스 찾을 수 없음
>
> **500**
>
> - Internal Server Error
> - 서버 내부 오류

**1️⃣ GET**

```js
// 방법 1️⃣ : path variable
// http://xxxx/blogs/id=1
const responseBlog = await api.get(`{baseURL 뒤로 오는 나머지 주소}/${blogId}`);

// 방법 2️⃣ : queryString
// http://xxxx/blogs?id=1
// 주의 ) 배열로 받아와짐
const response = await api.get("{baseURL 뒤로 오는 나머지 주소}", {
  params: { id: blogId },
});
```

**2️⃣ POST**

```js
const response = await api.post("{baseURL 뒤로 오는 나머지 주소}", {
  생성할 데이터 객체 전달
});

// ex
const response = await api.post("blogs", {
  title: title,
  content:content
  })
```

---

## Styled-Components 사용

### `Styled`

```js
// MainPage.jsx
import styled from "styled-components";

// <div> 컴포넌트 생성
const Container = styled.div`
  width: 100%;
  max-width: 720px;
  // 직계 자식 요소 ➡️ & > *
  & > * {
    :not(:last-child) {
      margin-bottom: 16px;
    }
  }
`;

const MainPage = () => {
  return <Container></Container>;
};

export default MainPage;
```
