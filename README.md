### 브랜치 구조 & 전략

- 브랜치 구조
  - main - 실제 배포
  - dev - 배포전 테스트
  - feat/기능
- issue 및 pr 템플릿 작성하기 ( 템플릿 참조 : <a href="https://github.com/team-opensource-plus/dummy-generator" target="_blank">링크</a>)
- 브랜치 순서 (단독 작업일 경우는 issue 및 pr 템플릿 작성은 꼭 잊지말기)
  1. 기능을 완성한다.
  2. pull request를 요청한다
  3. 코드 리뷰 후 피드백 반영한다.
     - ⭐️기능이 완성 될 때 코드 리뷰⭐️
  4. 피드백 반영된 것을 dev에 merge 후 branch를 삭제한다.
  5. dev에서 정상동작할 경우 main에 merge한다.
     - ⭐️간단한 style, 긴급할 때를 제외하고는 merge는 꼭 같이한다⭐️

### 커밋 컨벤션

### 작성 규칙

- 제목(type), 본문(body), 꼬리말(footer)로 구성
- 각 부분은 줄바꿈으로 구분
- 본문은 명령형으로 작성할 것 -> feat : 적용 로그인 패스워드 정규식
- 꼬리말은 선택사항으로 관련된 이슈를 적을 떄 사용 여러개일 경우 쉼표로 구분
  - fix : 수정중 배열 중첩 #29, #30

#### 제목(type) : 본문 (필요시 설명까지)

| 제목(type) | 본문                                                             | 예시 ( 한국어로 통일 )                         |
| ---------- | ---------------------------------------------------------------- | ---------------------------------------------- |
| feat       | 새로운 기능을 추가한 경우                                        | feat : 적용 로그인 패스워드 정규식             |
| edit       | 현재 코드를 수정 했을 경우                                       | edit : 수정 로그인 패스워드 정규식             |
| fix        | 버그 수정                                                        | fix : 해결 key 에러                            |
| ui         | CSS 등 UI 디자인을 변경한 경우                                   | ui : 수정 로그인페이지 input width             |
| type       | type만 변경사항이 있을 때                                        | type : 수정 Floor type                         |
| hotfix     | 급하게 치명적인 에러를 고친 경우                                 | hotfix : 수정 api에러                          |
| style      | 가독성 개선                                                      | style : 삭제 스페이스바                        |
| refactor   | 기능의 변경은 없지만 로직의 변경이 있을 경우                     | refactor : 성능개선 좌석배치                   |
| comment    | 주석을 추가하거나 변경한 경우                                    | comment : 삭제 로그인 페이지 13번째 주석       |
| docs       | 문서를 수정한 경우                                               | docs : 수정 리드미                             |
| test       | 테스트를 할 때                                                   | test : 테스트 V2 업데이트                      |
| chore      | 환경설정에 대한 것들 (빌드 스크립트 수정, 패키지 매니징 설정 등) | chore : 설정 초기셋팅 , chore : 추가 리액트 퀼 |
| rename     | 파일 or 폴더명 수정하는 경우                                     | rename : 변경 login폴더 -> SignIn으로          |
| move       | 파일 or 폴더 옮기는 경우                                         | move : 이동 login -> SignIn폴더로              |
| remove     | 파일을 삭제하는 작업만 수행한 경우                               | remove : 삭제 asset.ts                         |

#### ⭐️자세한 설명이 필요한 경우 꼭 issue에 추가해주기⭐️

참고 : <a href="https://velog.io/@outstandingboy/Git-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80-%EA%B7%9C%EC%95%BD-%EC%A0%95%EB%A6%AC-the-AngularJS-commit-conventions#short-summary-%EC%9A%94%EC%95%BD-%EC%84%A4%EB%AA%85" target="_blank">링크</a>

## 코드 컨벤션

### 1. **들여쓰기**

**space와 tab을 섞어서 사용하지 않는다.**

들여쓰기는 항상 tab를 사용한다.

### 2. 문장의 종료

문장의 종료는 항상 ;을 붙여준다

### **상수는 영문 대문자 스네이크 표기법(Snake case)를 사용.**

```jsx
SYMBOLIC_CONSTANTS;
```

### **변수, 함수에는 카멜 케이스을 사용한다.**

```jsx
// 숫자, 문자, 불린
const dog;
const variableName;

// 배열 - 배열은 복수형 이름을 사용
const dogs = [];

// 정규표현식 - 정규표현식은 'r'로 시작
const rDesc = /.*/;

// 함수
function getPropertyName() {
  ...
}

// 이벤트 핸들러 - 이벤트 핸들러는 'on'으로 시작
const onClick = () => {};
const onKeyDown = () => {};

// 불린 반환 함수 - 반환 값이 불린인 함수는 'is'로 시작
const isAvailable = false;
```

- 이하 [TOAST UI 코딩 컨벤션](https://ui.toast.com/fe-guide/ko_CODING-CONVENTION)을 참고

### 타입 컨벤션

#### Type의 이름은, 파스칼 케이스로 해당 변수와 동일한 네이밍을 사용

```tsx
const post: Post = {};
```

#### 타입 vs. 인터페이스

- union이나 intersection이 꼭 필요할 때 type 을 사용

  ```ts
  type Foo = number | { someProperty: number };
  type Pick = Pick<Interface, "id">;
  ```

- extends 또는 implements 하고 싶을 때 interface 를 사용

  ```ts
  interface Foo {
    foo: string;
  }
  interface FooBar extends Foo {
    bar: string;
  }
  class X implements FooBar {
    foo: string;
    bar: string;
  }
  ```

- 이 외의 경우에는 그날 당신을 행복하게 하는 것이라면 무엇이든 사용

### 2. styled-components 사용시

- 일반 컴포넌트와 구분하기 위해 S를 붙여 사용

  ```jsx

  import * as S from "./styled"

  export default Function Btn(){

    return <S.Button></S.Button>
  }
  ```

## 린트 및 프리티어 설정

- 린트 설정
  ```jsx
  rules: {
    "no-console": "warn",
    "no-unused-vars": ["error", { argsIgnorePattern: "^_" }],
    "@typescript-eslint/no-unused-vars": ["error", { argsIgnorePattern: "^_" }],
    "@typescript-eslint/no-explicit-any": "error",
    "react-refresh/only-export-components": [
      "error",
      { allowConstantExport: true },
    ],
  },
  ```
- 프리티어 설정

  ```jsx
  파일 생성 후 붙여넣기
  .prettierrc

  {
  	"arrowParens": "avoid",
  	"singleQuote": false,
  	"semi": true,
  	"useTabs": false,
  	"tabWidth": 2,
  	"trailingComma": "all",
  	"printWidth": 80
  }
  ```

## Vite ( React ) 설정

### 절대 경로 설정

tsconfig.json

```json
{
  "compilerOptions": {
    "paths": {
      "@/*": ["*"]
    }
  },
  "include": ["src", "**/*.ts", "**/*.tsx"],
  "references": [{ "path": "./tsconfig.node.json" }]
}
```

vite.config.ts

```ts
import { defineConfig } from "vite";
import react from "@vitejs/plugin-react";

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  resolve: {
    alias: [{ find: "@", replacement: "/src" }],
  },
});
```
