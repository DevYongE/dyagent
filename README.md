# dyagent — 회사형 멀티에이전트 개발 하네스

Claude Code 플러그인. 메인 세션이 **대표(CEO)** 가 되어 직원 에이전트들을 지휘해 기능을 기획부터 QA까지 구현합니다.

## 조직도

```
대표 (메인 세션 — 회의 진행·지시·검수·납품)
├── 이리서 (iriseo)      자료조사 — 가장 먼저 실행 (haiku)
├── 김기획 (kimgihoek)   기획·명세·재루프 판정 (opus)
├── 유트렌 (yutren)      디자인 + 트렌드 조사 + 애니메이션 스펙 (sonnet)
├── 백엔진 (baekengine)  백엔드 구현 (sonnet)
├── 최프론 (choepron)    프론트 구현 (sonnet)
└── 오깐깐 (ohkkankkan)  QA — 코드 수정 금지, 판정만 (opus)
```

## 워크플로우

1. **회의** — 대표가 클라이언트(사용자)에게 기획·디자인·개발 관점의 질문 (최대 2라운드)
2. **조사** → **기획** → **디자인** → **구현(백+프론트 병렬)** → **QA**
3. QA FAIL 시 김기획이 원인 판정 → 설계부터 재루프 (최대 2회)
4. 완료 산출물은 지정한 **옵시디언 vault**에 저장

## 설치

```
/plugin marketplace add DevYongE/dyagent
/plugin install dyagent@dyagent-marketplace
```

## 사용

```
dyagent로 할 일 앱 만들어줘
```

첫 실행 시 옵시디언 vault 경로를 물어보고 `dyagent.config.json`에 저장합니다.
부분 재실행도 지원: "디자인만 수정해줘", "QA만 다시 돌려줘".

## 토큰 가이드

기능 1개 풀 사이클에 약 40만~80만 토큰 (모델 차등 + 회의/재루프 캡 + 트렌드 캐시로 억제).

## License

MIT
