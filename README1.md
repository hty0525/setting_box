# ⭐️ pr올리기 전에 꼭 작업 겸치는지 확인 ⭐️

## 브랜치 구조 & 전략

- 브랜치 구조
  - main - 실제 배포
  - dev - 배포전 테스트
  - 작업자/feat # 기능추가
  - 작업자/update # 요청사항
  - 작업자/fix # 긴급요청 or 버그수정

### Git Flow

#### default

1. 작업자 이름으로 만든 브랜치에서 작업
2. dev로 pr 후 기존 브랜치 삭제
3. dev에서 qr진행 후 main으로 pull req

#### 긴급 요청사항

1. 요청 사항이 겹칠 경우 작업자/fix1 넘버링으로 브랜치 명을 정한다
2. QA진행이 힘들경우 로컬 테스트 후 바로 main으로 pr 그 외에는 기본 플로우와 동일

## 커밋 컨벤션

### 제목(type) : 본문 (필요시 설명까지)

| 제목(type) | 본문                       | 예시 ( 한국어로 통일 )             |
| ---------- | -------------------------- | ---------------------------------- |
| feat       | 새로운 기능을 추가한 경우  | feat : 적용 로그인 패스워드 정규식 |
| update     | 현재 코드를 수정 했을 경우 | edit : 수정 로그인 패스워드 정규식 |
| fix        | 버그 수정                  | fix : 해결 key 에러                |

## 코드 컨벤션

### **상수는 영문 대문자 스네이크 표기법(Snake case)를 사용.**

```jsx
SYMBOLIC_CONSTANTS;
```

### **변수, 함수에는 카멜 케이스을 사용한다.**

```jsx
// 배열 - 배열은 끝에 List 사용
const userList = [];

// 불린 반환 함수 - 반환 값이 불린인 함수는 'is'로 시작
const isAvailable = false;

// 모달 혹은 팝업일 경우
const isCancelModalOpen = false;

// 함수 동사+명사
const closeModal = () => {};

// 이벤트 핸들러 - 이벤트 핸들러는 'on'으로 시작
const onClickBtn = () => {
  closeModal();
  // 일반 함수와 이벤트 핸들러를 구분해서 사용한다.
};

const onKeyDown = () => {};

// CURD

// c
const addProduct = () => {};

// r
const getProductList = () => {};

// u
const editProduct = () => {};

// d
const deleteProduct = () => {};

// tanstack query

const useDeleteProductQuery = () => {};

const useDeleteProductMutation = () => {};
```

- 이하 [TOAST UI 코딩 컨벤션](https://ui.toast.com/fe-guide/ko_CODING-CONVENTION)을 참고

### 타입 컨벤션

#### ⭐️ 피치못할 사정이 아닌 경우 제외 any 금지 ⭐️

- 예외사항
  1. 에측 불가능할때
  2. 해당 라이브러리에서 제공해 주지 않을때
  3. 제외 하고는 유추되는 타입은 값을 보면서라도 적용하기

#### Type의 이름은, 파스칼 케이스로 해당 변수와 동일한 네이밍

```ts
const ex: Extends = {
  name: "이름",
  age: 0,
};

type Ex = {
  name: string;
};

type Extends = Ex & {
  age: number;
};

// api 타입은 요청 주소와 맞춰서 사용한다
// [get] /api/setting/user
// 요청/응답 + 메서드 + api주소
type ResGetSettingUser = {};

// params혹은 body가 있을 경우
type ReqGetSettingUserParams = {};

type ReqGetSettingUserBody = {};
```
