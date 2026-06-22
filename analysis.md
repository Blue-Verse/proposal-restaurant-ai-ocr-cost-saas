# 외식업 전용 AI 거래명세서 OCR 및 원가 관리 SaaS 플랫폼 구축 — 제안 분석 로그

> 생성일: 2026-06-22
> 공고 URL: https://www.wishket.com/project/156255/

## 1. 공고 파싱 결과

```yaml
job:
  title: "외식업 전용 AI 거래명세서 OCR 및 원가 관리 SaaS 플랫폼 구축"
  category: "SaaS·솔루션 / 웹·안드로이드·iOS / 데이터 분석·BI / 통계·대시보드"
  budget_range: "40,000,000원 (평균 지원 34,600,000원 / 최저 0 / 최고 40,000,000원)"
  duration: "90일 (희망: 착수 후 3~4개월 내 협의)"
  tech_stack: [React, React Native, Supabase, Vercel, "GPT-4o Vision API 또는 Claude API"]
  description: >
    외식업 종사자가 스마트폰으로 식자재 거래명세서를 촬영하면 AI가 품목·단가를
    자동 추출하고, 사용자 교정 데이터로 스스로 재학습하는 파이프라인을 포함한
    B2B SaaS 플랫폼. 식자재→프렙→메뉴 3단계 원가 계산 엔진과 마진율 대시보드 제공.
  requirements:
    - "AI Vision OCR: 카메라 촬영·업로드, Vision API 기반 품목·수량·단가·공급업체 JSON 추출"
    - "외식업 전용 품목명 사전 기반 이표기 자동 매핑"
    - "사용자 교정 UI + 교정 데이터 활용 자동 재학습 파이프라인"
    - "식자재→프렙→메뉴 3단계 계층 DB 및 단가 변경 연쇄 자동 업데이트"
    - "목표 원가율 설정·초과 시 실시간 푸시 알림"
    - "메뉴별 원가율·마진율 차트, 월 고정비·인건비 기반 수익 구조 진단"
    - "Supabase Auth 회원가입/로그인 + 개인정보보호법 동의 UI"
    - "React Native 모바일 앱 + React 웹 대시보드"
    - "최고 관리자 백오피스: 식당 관리, 글로벌 품목 사전 마스터, API 통계·에러 로그"
    - "비기능: Vision API 지연 대응 로딩 UX, Supabase RLS 식당 간 데이터 격리"
  client_questions: []
  deadline: "2026-06-29"
  job_post_url: "https://www.wishket.com/project/156255/"
  urls: []
  images: []
  client_location: "경기도 과천시"
  meeting: "온라인 (화상·전화)"
```

## 2. URL/이미지 분석

참고 URL/이미지 없음 — 공고 본문에 레퍼런스 사이트·Figma·이미지 첨부가 포함되지 않음. 원본 공고 링크(위시켓)만 존재.

## 3. 실현 가능성 분석 (내부용)

- **프로젝트 유형**: 풀스택 SaaS + 모바일 앱(RN) + 외부 LLM Vision API 연동 (복합)
- **기본 공수(개략, AI 보조 없이)**: 약 145 M/D
  - 기획/설계 ~30, 디자인 ~16, AI OCR/재학습 ~30, 원가 엔진 ~26, 모바일 앱 ~22(+학습), BE/Supabase ~16, 관리자 ~14, QA ~15
- **버퍼**: 모바일(+20%) + 외부 API(+15%) 반영
- **1인 환산 기간**: 약 126 달력일 → 클라이언트 예상 90일 초과
- **판정**: 1인 기준으로는 90일 초과이나, **다수 인력 병행 투입 시 기획·디자인·개발 단계 중첩으로 90일 유지 가능** (메모리 기록 패턴과 일치)

## 4. 포트폴리오 매칭

매칭 우선순위(기술 40 / 도메인 30 / 기능 20 / 규모 10) 기준 상위 3:

1. **Harmony Link** (B2B SaaS·헬스케어) — 멀티테넌트 데이터 격리(= Supabase RLS 식당 격리), AI 데이터 분석, 모바일+웹+관리자 크로스플랫폼. 본 프로젝트 구조와 최상위 대응.
2. **AI Agent** (AI/자동화) — LLM(Claude) 연동, 구조화 JSON 추출, 검증·재처리 루프 = Vision OCR + 자동 재학습 파이프라인 역량.
3. **EZ-Approve** (B2B SaaS·어드민) — 관리자 백오피스/대시보드, RBAC·데이터 접근 제어, 상태 연쇄 워크플로우 = 관리자 + 원가 연쇄 업데이트.

(보조 후보: Connectin — OCR 명함 스캔/크로스플랫폼 / Calendar Share — Supabase / Pilates App — React Native)

## 5. 최종 제안 요약

- **지원 금액**: 34,000,000원 (VAT 별도) — 클라이언트 예상 40,000,000원의 85%
- **지원 기간**: 90일 (클라이언트 예상 유지, 다수 인력 병행)
- **핵심 제안 포인트**:
  1. Vision API 추출 + 외식업 품목 사전 매핑 + 사용자 교정 데이터 재학습 루프
  2. 식자재→프렙→메뉴 3단계 원가 엔진, 단가 변경 연쇄 자동 업데이트 + 목표 원가율 푸시
  3. Supabase RLS 기반 완벽한 식당 단위 데이터 격리(멀티테넌트)
  4. iOS·Android 앱 + 웹 대시보드 + 관리자 백오피스 단일 데이터 모델 통합 제공
  5. Vision API 지연 대응 비동기·로딩 UX

## 6. 최종 산출물 (8단계 출력 전문)

### 제안서 사이트 URL
https://proposal-router.claude-ai-b27.workers.dev/proposal-restaurant-ai-ocr-cost-saas/

### 지원 금액
34,000,000원 (VAT 별도) — 클라이언트 예상 40,000,000원의 85%

### 지원 기간
90일

### 클라이언트 질문 답변
해당 없음 (공고에 클라이언트 작성 질문 없음)

### 지원 내용 (전체 텍스트)
안녕하세요, 외식업 전용 AI 거래명세서 OCR 및 원가 관리 SaaS 플랫폼 구축 프로젝트에 지원합니다.

본 프로젝트에 대한 상세 제안서(견적서, 공수계산서, PRD, 일정, 포트폴리오)를 별도 페이지로 준비하였습니다. 아래 링크에서 확인해 주시면 감사하겠습니다.
▶ 제안서 상세 페이지: https://proposal-router.claude-ai-b27.workers.dev/proposal-restaurant-ai-ocr-cost-saas/
▶ 위시켓 포트폴리오: https://www.wishket.com/partners/p/blueverse1/

---

<프로젝트 진행 제안>

■ 프로젝트 분석
- 거래명세서 촬영 한 번으로 품목·수량·단가·공급업체를 구조화 데이터로 자동 추출하고, 사용자 교정 데이터를 축적해 인식 정확도를 스스로 높이는 재학습 파이프라인을 구축합니다.
- 외식업 전용 품목명 사전 기반 이표기 자동 매핑으로 현장 표기 차이를 흡수합니다.
- 식자재→프렙→메뉴 3단계 계층 원가 엔진을 설계하여, 식자재 단가가 바뀌면 관련 메뉴 원가율이 연쇄 자동 업데이트되고 목표 원가율 초과 시 실시간 푸시로 알립니다.
- Supabase RLS로 식당 간 데이터를 행 단위로 완전 격리하고, iOS/Android 앱·웹 대시보드·최고 관리자 백오피스를 단일 데이터 모델 위에서 일괄 제공합니다.
- Vision API 응답 지연은 비동기 처리와 진행률·스켈레톤 로딩 UX로 자연스럽게 흡수합니다.

■ 작업 일정

[Phase 1] 기획 & 디자인 (Day 1–20)
- 요구사항 정의, 화면 설계, 식자재→프렙→메뉴 3단계 데이터 모델링, API 명세, 모바일·웹·관리자 Figma 디자인

[Phase 2] 백엔드 & AI Vision OCR 파이프라인 (Day 18–50)
- Supabase Auth·RLS·스키마, Vision API 연동 및 JSON 추출, 품목 사전 매핑, 교정 UI 및 재학습 파이프라인

[Phase 3] 원가 엔진 & 앱/웹 대시보드 (Day 40–72)
- 3단계 원가 엔진·연쇄 자동 업데이트, 목표 원가율 푸시 알림, React Native 앱·React 웹 대시보드

[Phase 4] 관리자 백오피스 & 통합 (Day 65–80)
- 식당 관리, 글로벌 품목 사전 마스터, API 호출 통계·에러 로그 모니터링 관리자 웹 및 전체 통합

[Phase 5] QA & 배포 (Day 80–90)
- 통합 테스트, 로딩 UX·RLS 격리 검증, Vercel·앱 스토어 배포, 관리자 매뉴얼

■ 마일스톤 및 산출물
- M1(Day 20): 기획·디자인 완료 — 요구사항 정의서, ERD, API 명세, Figma
- M2(Day 50): OCR 파이프라인 동작 — 촬영→추출→교정→재학습 시연
- M3(Day 72): 원가 엔진·대시보드 — 연쇄 업데이트·푸시·마진 대시보드 시연
- M4(Day 80): 관리자·통합 완료
- M5(Day 90): 최종 배포 — 소스코드, 기획·디자인 원본, 관리자 매뉴얼 인계

■ 미팅 시 협의 필요 사항
- 초기 외식업 품목명 사전 엑셀 데이터의 범위 및 포맷
- Vision API 선택(GPT-4o Vision / Claude) 및 비용 부담 주체
- 재학습 파이프라인의 적용 수준(프롬프트·매핑 규칙 보정 vs 모델 파인튜닝)
- 앱 스토어 등록 계정 및 푸시 알림 발송 정책

---

<유사 프로젝트 진행 경험>

▶ Harmony Link — 시니어 주간보호 관리 플랫폼 (약 6개월)
- 프로젝트 유형: B2B SaaS / 멀티테넌트 / 헬스케어
- 핵심 기능: 멀티테넌트 데이터 격리, AI 기반 건강 데이터 분석, 모바일+웹+관리자 6 플랫폼 통합, 140+ API
- 유사점: 식당 단위 데이터 격리(Supabase RLS)와 동일한 멀티테넌트 설계, AI 데이터 처리, 모바일 앱·웹·관리자 백오피스 동시 제공
- 기술 스택: Flutter, NestJS, Next.js, React, AWS

▶ AI Agent — LLM 기반 자동화 파이프라인
- 프로젝트 유형: AI / 자동화
- 핵심 기능: LLM(Claude) 연동 구조화 JSON 추출, 품질 게이트 검증·재처리 루프, 규칙 기반 지속 개선
- 유사점: 이미지에서 LLM Vision으로 JSON을 추출하고 교정 데이터로 정확도를 높이는 재학습 파이프라인과 동일 역량
- 기술 스택: TypeScript, Claude API, MCP, React, PostgreSQL

▶ EZ-Approve — 전자결재 SaaS & 관리자 대시보드 (약 9주)
- 프로젝트 유형: B2B SaaS / 기업용 어드민
- 핵심 기능: 관리자 백오피스·대시보드, RBAC·6계층 보안, 상태 연쇄 결재 워크플로우, 120-150 API
- 유사점: 최고 관리자 백오피스(식당·품목 사전·통계·로그)와 단가 변경이 메뉴 원가율로 연쇄되는 자동 업데이트 로직 구현 경험
- 기술 스택: NestJS, Next.js, TypeScript, MySQL, Docker

---

<사용 기술과 툴>

▶ 개발 기술
- 모바일 앱: React Native (iOS/Android)
- 웹: React.js
- 백엔드·DB: Supabase (PostgreSQL, Auth, RLS, Edge Functions)
- AI 연동: GPT-4o Vision API 또는 Anthropic Claude API
- 인프라·배포: Vercel

▶ 개발 도구 및 인프라
- 버전 관리: GitHub
- CI/CD: GitHub Actions
- 클라우드: Supabase / Vercel
- 푸시 알림: Push Notification 연동

▶ 커뮤니케이션
- 일일 진행 공유: Slack 또는 카카오톡
- 주간 미팅: Zoom / Google Meet (온라인)
- 문서 공유: Notion 또는 Google Docs
- 이슈 트래킹: GitHub Issues

### 관련 포트폴리오 추천
1. Harmony Link — 멀티테넌트 B2B SaaS + AI 분석 + 모바일·웹·관리자 통합
2. AI Agent — LLM 연동·구조화 추출·재학습 루프
3. EZ-Approve — 관리자 백오피스 + 데이터 접근 제어 + 연쇄 업데이트 워크플로우
