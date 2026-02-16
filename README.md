> **⚠️ 다른 컴퓨터에서 작업 시 주의사항 (2026-02-16)**
>
> 이 레포는 GitHub contributor 캐시 정리를 위해 **삭제 후 재생성**되었습니다.
> 다른 컴퓨터에 기존 clone이 있다면 **삭제 후 새로 clone** 해주세요:
> ```bash
> rm -rf ai-workflow
> git clone https://github.com/rometemp0613/ai-workflow.git
> ```
> **이 안내는 모든 컴퓨터에서 새로 clone한 후 삭제해주세요.**

# AI Workflow - 멀티 에이전트 협업 학습

**학습 방식**: Claude Code 멀티 세션 실습
**학습 시작일**: 2026-01-31
**목표**: 계층적 멀티 에이전트 시스템 구축 및 운영

---

## 최종 목표 구조

```
메인 오케스트레이터
├── 백엔드 리더
│   ├── API 워커
│   ├── DB 워커
│   └── Auth 워커
├── 프론트엔드 리더
│   ├── UI 워커
│   ├── State 워커
│   └── Style 워커
└── 테스트 리더
    ├── Unit 워커
    ├── Integration 워커
    └── E2E 워커
```

---

## 진도 체크리스트

### Part 1: 기초 환경 설정

- [x] **1.1 tmux 설치 및 기본**
  - 핵심: 설치, 세션 생성/종료, 창 분할, 세션 전환

- [ ] **1.2 tmux 실전 단축키**
  - 핵심: prefix 키, 창 분할, 복사 모드, .tmux.conf

- [ ] **1.3 Claude Code 설치와 첫 사용**
  - 핵심: CLI 설치, 기본 대화, /help, 작업 디렉토리 개념

### Part 2: Claude Code 기본 기능

- [ ] **2.1 CLAUDE.md 고급 활용**
  - 핵심: 프로젝트/폴더별 지침서, 계층 구조, Auto Memory 연동

- [ ] **2.2 Memory 시스템과 컨텍스트 관리**
  - 핵심: Auto Memory, /memory 명령, 세션 간 지식 유지

- [ ] **2.3 Session 관리**
  - 핵심: -c continue, -r resume, --session-id, 긴 작업 이어하기

- [ ] **2.4 Permissions와 Tool Rules**
  - 핵심: allowlist/denylist, settings.json, 보안 설정

- [ ] **2.5 Print Mode (Headless)**
  - 핵심: -p 플래그, 비대화형 실행, 파이프라인/스크립트 연동

### Part 3: Claude Code 확장 기능

- [ ] **3.1 Skills (슬래시 커맨드)**
  - 핵심: SKILL.md 작성, 커스텀 /명령어, 반복 작업 자동화

- [ ] **3.2 Hooks (동기 + 비동기)**
  - 핵심: PreToolUse/PostToolUse, 린트 자동화, Async Hooks

- [ ] **3.3 MCP 서버 기초**
  - 핵심: MCP 개념, claude mcp add, stdio/SSE, 기본 연결

- [ ] **3.4 MCP 서버 실전**
  - 핵심: GitHub MCP, 파일시스템 MCP, 커스텀 MCP, 멀티 서버

### Part 4: 서브에이전트와 자동화

- [ ] **4.1 빌트인 Subagents**
  - 핵심: Task 도구(Explore, Plan, Bash), 자동 위임, 병렬 실행

- [ ] **4.2 Agent SDK 기초**
  - 핵심: Python/TypeScript SDK, 프로그래밍 방식 호출, 구조화된 출력

- [ ] **4.3 Agent Teams (실험 기능)**
  - 핵심: 팀원 정의, 에이전트 간 직접 소통, 병렬 실행, 분산 작업

- [ ] **4.4 Plugins**
  - 핵심: Skills+Hooks+MCP 패키징, 배포/공유, 프로젝트별 조합

### Part 5: 멀티 세션 협업

- [ ] **5.1 tmux + Claude Code 세션 운영**
  - 핵심: 여러 세션 띄우기, 세션별 작업 디렉토리, 세션 간 전환

- [ ] **5.2 파일 기반 통신 규약 설계**
  - 핵심: .workflow/tasks/, outputs/, status.json, JSON 프로토콜

- [ ] **5.3 메인 + 워커 협업 (1:N)**
  - 핵심: 오케스트레이터 + 워커 N개, 작업 분배/수집, 병렬 실행

- [ ] **5.4 에러 처리와 모니터링**
  - 핵심: 실패 감지, 작업 재할당, 로그 수집, 진행 추적

### Part 6: 계층적 멀티 에이전트 시스템

- [ ] **6.1 리더 세션 설계**
  - 핵심: 리더 역할, 메인-리더 통신, 하위 워커 관리 CLAUDE.md

- [ ] **6.2 팀별 구성 실습**
  - 핵심: 백엔드/프론트/테스트 3팀 동시 구성, 리더+워커 운영

- [ ] **6.3 전체 시스템 통합**
  - 핵심: 메인↔리더↔워커 3계층, 크로스 팀 의존성, 통합 상태 관리

- [ ] **6.4 GitHub Actions 통합**
  - 핵심: @claude 멘션, PR 자동 리뷰, CI/CD에 Claude 삽입

### Part 7: 실전 프로젝트와 고급 패턴

- [ ] **7.1 실전 프로젝트 - 설계와 개발**
  - 핵심: 웹앱 선정, 멀티 에이전트로 작업 분배, 실제 개발

- [ ] **7.2 실전 프로젝트 - 통합과 회고**
  - 핵심: 결과물 통합, 병목 분석, 단독 vs 멀티 비교

- [ ] **7.3 자동화 종합 - 원클릭 시스템**
  - 핵심: 세션 자동 생성, 작업 자동 분배, 모니터링 대시보드

---

## 학습 일지

| 날짜 | 주제 | 주요 내용 | 비고 |
|------|------|----------|------|
| 2026-01-31 | 1.1 tmux 기본 | 세션 생성/종료, detach/attach, Ctrl+b,s 전환 | 첫 수업! |

---

## 진행 현황

- **총 항목**: 27개
- **완료**: 1개
- **진행률**: 4%

---

## 참고 자료

- [tmux 치트시트](https://tmuxcheatsheet.com/)
- Claude Code 공식 문서

---

## 메모

- 실습용 프로젝트는 `ai-workflow/practice/` 에 생성
- 각 실습마다 별도 폴더로 관리
