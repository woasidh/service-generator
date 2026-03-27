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
   3. todo: global/prompt/create_project_overview.md 작성, global/template/project_overview.md 작성 

---

### 기능 명세서 작성
1. AI가 프로젝트 개요서보고 기능 명세서 작성 / 피드백
   1. input: global/project_overview.md 
   2. output: global/feature.md
   3. todo: global/prompt/create_feature.md 작성, global/template/feature.md 작성

---

### 디자인 컨셉 및 디자인시스템 선정
1. AI가 프로젝트 개요, 기능 명세서 기반으로 디자인 컨셉 작성
   1. input: output/project_overview.md, output/feature.md 
   2. output: design file, design_overview.md
   3. todo: design/prompt/create_design_overview.md 작성, design/template/design_overview.md 작성
2. 사람이 피드백
   1. input: user feedback
   2. output: design file update, design_overview.md update
   3. todo: design/prompt/user_feedvback.md 작성

---

### 프로젝트 설계 및 생성

#### BE 개발
1. AI가 백엔드 프로젝트 설계 md 작성
   1. input: output/feature.md
   2. output: output/be_project_build.md
   3. todo: be/prompt/create_be_project_build.md 작성, be/template/be_project_build.md 작성
2. AI가 백엔드 프로젝트 및 프레임워크 개발
   1. input: output/be_project_build.md
   2. output: be project source code, output/be_project_convention.md
   3. todo: be/prompt/create_be_project.md 작성, be/template/be_project_convention.md 작성

#### FE 개발
1. AI가 FE 프로젝트 설계 md 작성
   1. input: output/feature.md
   2. output: output/fe_project_build.md
   3. todo: fe/prompt/create_fe_project_build.md 작성, fe/template/fe_project_build.md 작성
2. AI가 FE 프로젝트 및 프레임워크 개발
   1. input: output/fe_project_build.md
   2. output: fe project source code, output/fe_project_convention.md
   3. todo: fe/prompt/create_fe_project.md 작성, fe/template/fe_project_convention.md 작성

---

### 신 기능 개발 (기능 명세서 n개 기능 반복)

#### 디자인 명세
1. 디자인 명세 작성
   1. input: output/feature.md
   2. output: design file update
   3. todo: design/prompt/create_design_feature.md 작성 작성

#### BE 개발
1. 기능 개발 md 작성
   1. input: output/feature.md
   2. output: output/be_feature.md
   3. todo: be/prompt/create_be_feature.md 작성, be/template/be_feature.md 작성
2. 기능 개발
   1. input: output/be_feature.md
   2. output: be feature source code
   3. todo: be/prompt/implement_be_feature.md 작성

#### FE 개발
1. 기능 개발 md 작성
   1. input: output/feature.md
   2. output: output/fe_feature.md
   3. todo: fe/prompt/create_fe_feature.md 작성, fe/template/fe_feature.md 작성
2. 기능 개발
   1. input: output/fe_feature.md
   2. output: fe feature source code
   3. todo: fe/prompt/implement_fe_feature.md 작성

---

### 유지보수 (todo)

---

### QA
개발 단계에서 테스트코드로 대부분 커버
e2e는 지금은 사람이 하기
e2e 자동화 시킬 수 있는 부분 자동화 시키기
---

### 배포 단계
code push로 pipeline trigger (github action)

---