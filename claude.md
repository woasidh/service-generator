## 응답 지침
- 사용자에게서 부족한 정보가 있으면 물어볼 것
- 추가적으로 제안할 내용이 있으면 물어보고 적용할 것

## 목표
- 1인 서비스 앱 개발을 하려고해
- 아이디어, 기획, 디자인, 개발까지 하려고해
- claude code (mcp 포함)를 적극 활용해서 위 과정을 자동화 할거야.
- 각 단계에서 쓰이는 prompt, template등을 관리할거야.
---

## 서비스 개발 플로우 
### 프로젝트 개요서 작성
1. 유저가 아이디어 제시
2. 제시된 아이디어 기반으로 AI가 프로젝트 개요서 고도화
   1. input: idea from user
   2. output: global/project_overview.md

---

### 기능 명세서 작성
1. AI가 프로젝트 개요서보고 기능 명세서 작성 / 피드백
   1. input: global/project_overview.md 
   2. output: global/feature.md

---

### 디자인 컨셉 및 디자인시스템 선정
1. AI가 프로젝트 개요, 기능 명세서 기반으로 디자인 컨셉 작성
   1. input: output/project_overview.md, output/feature.md 
   2. output: multiple concepts of images (design/concepts/image_concept_01.md, design/concepts/image_concept_02.md, ...)
   3. todo: stitch sdk 통해서 컨셉 뽑는 prompt 작성
2. 사람이 피드백
   1. input: user feedback
   2. output: 

---

### 신 기능 개발 (기능 명세서 n개 기능 반복)

#### 디자인 명세
1. 디자인 명세 작성
   1. input: global/output/feature.md
   2. output: design/**.png
   3. todo: stitch sdk 사용해서 필요하면 화면 명세 뽑는 프롬프트 작성

#### supabase 수정
1. supabase 
   1. input: global/output/feature.md, supabase/schema.md
   2. output: supabase schema update (mcp server), update supabase/schema.md

#### FE 개발
1. 기능 개발
   1. input: global/output/feature.md, supabase/schema.md, design/resources/**
   2. output: fe feature source code
   3. todo: fe/prompt/implement_feature.md (스펙명 인자 필수)

---

### QA
개발 단계에서 테스트코드로 대부분 커버
e2e는 지금은 사람이 하기
e2e 자동화 시킬 수 있는 부분 자동화 시키기
---

### 배포 단계
code push로 pipeline trigger (github action)

---