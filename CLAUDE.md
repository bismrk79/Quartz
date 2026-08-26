# CLAUDE.md - PurpleLeaf Vault 지시 파일

## Vault 구조
- 1_Projects/ : 진행 중인 프로젝트 (비공개)
- 2_Areas/ : 지속 관리 영역 (선택 공개)
- 3_Resources/ : 참고 자료 (선택 공개)
- 4_Archives/ : 완료/보관 (비공개)
- 99_System/ : 시스템 파일 (비공개)

## 새 노트 작성 규칙
1. 기존 파일 먼저 확인, 중복 생성 금지
2. 관련 개념에 [[링크]] 추가
3. 파일당 하나의 개념 (원자적 노트)
4. frontmatter 필수 포함:

공개 노트:
---
is_public: true
tags: [태그1, 태그2]
date: YYYY-MM-DD
---

비공개 노트:
---
draft: true
---

## 커밋 메시지 규칙
- add: 새 노트 추가
- update: 기존 노트 수정
- link: 노트 간 연결 추가
- fix: 오류 수정

## 공개 기준
- 성경 묵상, 신학 연구 → is_public: true 권장
- 개인 일정, 비즈니스 메모 → draft: true
