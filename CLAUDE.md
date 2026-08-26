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

## 배포 파이프라인
```
Obsidian 노트 작성
      ↓
Obsidian Git 플러그인 (Ctrl+P → "Git: Commit-and-sync")
      ↓
GitHub 저장소 (bismrk79/Quartz)
      ↓
GitHub Actions 자동 실행 (deploy.yml)
      ↓
bismrk79.github.io/Quartz 자동 배포
```
- Vault 자체가 `E:\PL\quartz`이고 `.git`도 그 안에 있음 → Obsidian Git 설정의 **Custom base path는 비워둘 것** (상위 경로로 설정하면 "Can't find a valid git repository" 오류 발생)
- draft 필터: `quartz.config.yaml`에 `@quartz-community/remove-draft` 활성화됨 → `draft: true` 노트는 자동으로 배포 제외
- `explicit-publish`는 비활성화 상태 → `is_public` 명시 없어도 기본적으로 공개됨 (draft로만 비공개 제어)
- 일상 워크플로우: 노트 작성 → `Ctrl+P` → `Git: Commit-and-sync` → 1~2분 후 사이트 자동 반영
