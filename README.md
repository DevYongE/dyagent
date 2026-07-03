# dyagent — 회사형 멀티에이전트 개발 하네스

Claude Code 플러그인. 메인 세션이 **대표(CEO)** 가 되어 직원 에이전트들을 지휘해 기능을 기획부터 QA까지 구현합니다.

## 조직도

```
대표 (메인 세션 — 회의 진행·지시·검수·납품)
├── 개발팀
│   ├── 이리서 (iriseo)      자료조사 — 가장 먼저 실행 (haiku)
│   ├── 김기획 (kimgihoek)   기획·명세·재루프 판정 (opus)
│   ├── 유트렌 (yutren)      디자인 + 트렌드 조사 + 애니메이션 스펙 (sonnet)
│   ├── 백엔진 (baekengine)  백엔드 구현 (sonnet)
│   └── 최프론 (choepron)    프론트 구현 (sonnet)
├── 검증
│   ├── 오깐깐 (ohkkankkan)  내부 QA — 코드 수정 금지, 판정만 (opus)
│   └── 박코덱 (bakcodek)    외주 검증 — OpenAI Codex CLI, 미설치 시 설치 (sonnet)
└── 마케팅팀
    ├── 한스샷 (hanshot)     스크린샷 촬영·보정 (sonnet)
    ├── 나블로 (nabeullo)    블로그 글 + SEO (sonnet)
    ├── 임스타 (imsta)       인스타 캐러셀·캡션·해시태그·릴스 (haiku)
    └── 정튜브 (jeongtube)   유튜브 대본·영상/채널 컨셉·썸네일 (sonnet)
```

## 워크플로우

1. **회의** — 대표가 클라이언트(사용자)에게 기획·디자인·개발 관점의 질문 (최대 2라운드)
2. **조사** → **기획** → **디자인** → **구현(백+프론트 병렬)** → **검증(내부 QA + 외주 Codex 병렬)**
3. 검증 FAIL 시 김기획이 원인 판정 → 설계부터 재루프 (최대 2회)
4. 완료 산출물은 지정한 **옵시디언 vault**에 저장
5. **마케팅(선택)** — 스크린샷 촬영 후 블로그·인스타·유튜브 콘텐츠 병렬 제작

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
