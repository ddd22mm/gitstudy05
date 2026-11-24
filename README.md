# hello-nest

『TypeScript-NestJS 완전정복』 14장 실습 프로젝트입니다.
NestJS 12, TypeScript, ESM과 Vitest를 사용합니다.

## 설치 및 실행

Node.js 22.12 이상과 npm이 필요합니다.

```powershell
npm ci
Copy-Item .env.example .env
npm run start:dev
```

이미 `.env`가 있으면 복사 단계를 건너뜁니다.
http://localhost:3000/ 에 접속하면 `Hello World!`가 표시됩니다.
파일 저장 시 자동으로 재시작하며, 종료는 Ctrl+C입니다.
포트는 `.env`의 `PORT`로 변경할 수 있습니다.

## API 호출

WebStorm에서 `requests.http`를 열고 GET 요청 왼쪽의 실행 버튼을 누릅니다.
터미널에서는 `curl.exe http://localhost:3000/`을 실행합니다.
응답은 HTTP 200과 `Hello World!`입니다.

## 주요 명령어

| 명령어 | 용도 |
| --- | --- |
| `npm run start:dev` | 개발 서버 실행 |
| `npm run build` | dist/에 빌드 |
| `npm run start:prod` | 빌드 결과 실행 |
| `npm run lint` | 코드 검사 |
| `npm run format` | 코드 정렬 |
| `npm test` | 단위 테스트 |
| `npm run test:e2e` | HTTP 응답 테스트 |

## 코드 구조

- `src/main.ts`: 앱 생성과 포트 설정
- `src/app.module.ts`: 컨트롤러와 서비스 등록
- `src/app.controller.ts`: GET / 요청 처리
- `src/app.service.ts`: Hello World! 반환
- `src/app.controller.spec.ts`: 단위 테스트
- `test/app.e2e-spec.ts`: HTTP 200과 응답 본문 검증

책의 기본 구조에 기존 CLI가 생성한 NestJS Observe 연동을 유지했습니다.
연동 키는 로컬 `.env`에서만 관리하며 Git에 올리지 않습니다.
node_modules/와 dist/도 Git에서 제외합니다.
