## 폴더 구조

```
.
├──api
│ └── index.ts      # api 기본 설정 ex) axios instance
├── app
│ ├── _components   # 페이지에서 사용되는 컴포넌트
│ ├── _hooks        # 페이지 관련 훅 비지니스 로직 포함
│ ├── _apis         # 페이지 관련 api
│ ├── _provider     # 페이지 관련 provider
│ ├── _type         # 페이지 관련 type
│ ├── favicon.ico
│ ├── globals.css
│ ├── layout.tsx
│ └── page.tsx      # page가 container 역할로
├── config          # 환경변수
│ └── [name].env
├── components
│ └── common        # 전역에서 사용할 수 있는 컴포넌트
│   ├── Button.tsx
│   ├── Input.tsx
│   └── index.ts    # 모든 전역 컴포넌트는 index에서 export
├── [Component]     # 2곳 이상에서 사용되는 컴포넌트 폴더로 구분
│   └── index.tsx
├── utils           # 유틸리티 함수
├── hook            # 전역에서 사용되는 hook
├── constants       # 전역에서 사용되는 상수
├── store           # 전역 상태 관리 ex) zustand
├── styles          # 전역 스타일
└── README.md
```

참고 : <a href="https://velog.io/@fenjo/3-layers-architecture-%ED%94%84%EB%A1%A0%ED%8A%B8%EC%97%94%EB%93%9C-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EA%B5%AC%EC%A1%B0%EB%A5%BC-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B5%AC%EC%84%B1%ED%95%98%EA%B3%A0-%EC%9E%88%EB%82%98%EC%9A%94" target="_blank">3 레이어 구조</a>

걱정되는 점은 app 폴더 안에 저렇게 해도 될까?

app 폴더 안에는 클린하게 유지 되어야 하는게 아닐까?

```
.
├── features/            # 기능별 모듈 디렉토리
│   ├── auth/            # 인증 기능 (로그인, 회원가입 등)
│   │   ├── components/  # 인증 관련 컴포넌트
│   │   ├── hooks/       # 인증 관련 커스텀 훅
│   │   ├── api/         # 인증 관련 api
│   │   ├── pages/       # 인증 관련 페이지
│   │   ├── types/       # 인증 관련 타입 (typescript 사용시)
│   │   ├── constants/   # 인증 관련 상수 값
│   │   └── utils/       # 인증 관련 유틸리티 함수
│   └── [other features] # 다른 기능들
│
├── app/                 # Next.js app 라우팅
│   └── page.tsx         # features 내부의 pages와 연결
│   └── layout.tsx
│
├── components/          # 전역에서 사용되는 재사용 가능한 컴포넌트
├── hooks/               # 전역에서 사용되는 커스텀 훅
├── api/                 # 전역에서 사용되는 api
├── utils/               # 전역 유틸리티 함수
├── types/               # 전역에서 사용되는 타입 (typescript 사용시)
├── constants/           # 전역에서 사용되는 상수 값
├── store/               # 전역 상태 관리 (예: Context API, Redux, recoil, zustand 등)
└── styles/              # 전역 스타일
```

추후에 서버컴포넌트, 클라이언트 컴포넌트 어떻게 나눌지도 생각 해봐야 할 것 같음

참고 : <a href="https://bluemiv.tistory.com/87" target="_blank">기능 별 구조</a>
