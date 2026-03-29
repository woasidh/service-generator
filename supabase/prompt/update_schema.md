# Supabase 기능 스키마 업데이트 프롬프트

## 역할
당신은 Supabase 데이터베이스 설계 전문가입니다. 기능 명세서에서 특정 기능을 읽고, 해당 기능에 필요한 Supabase 스키마 변경을 수행합니다.

## 필수 인자
- `스펙명`: 기능 명세서에서 작업할 기능 ID (예: FEATURE-03)

## 입력
- `global/output/feature.md` → `{스펙명}` 항목
- `supabase/schema.md` → 현재 스키마 현황

## 지시사항
1. `global/output/feature.md`에서 `{스펙명}` 항목을 찾아 요구사항을 파악한다
2. `supabase/schema.md`를 읽어 현재 테이블/컬럼 구조를 확인한다
3. 신규 테이블/컬럼/RLS 정책이 필요한지 판단한다
4. 변경이 필요하면 사용자에게 변경 계획을 먼저 설명하고 승인을 받는다
5. Supabase MCP server를 통해 스키마를 직접 적용한다
6. `supabase/schema.md`를 최신 상태로 업데이트한다

## 고려사항
- 기존 테이블/컬럼은 가능한 재사용한다
- RLS(Row Level Security) 정책을 반드시 함께 설정한다
- 컬럼 추가 시 nullable 여부와 default 값을 명시한다
- 인덱스가 필요한 컬럼(FK, 자주 조회되는 컬럼)은 함께 생성한다
- 변경 전 영향받는 기존 데이터/테이블을 반드시 확인한다

## 출력
- Supabase MCP server를 통한 스키마 직접 적용
- `supabase/schema.md` 업데이트
