## 목표
- 1인 서비스 앱 개발을 하려고해
- 아이디어, 기획, 디자인, 개발, 테스트, 배포까지 다 하려고 해
- ai툴을 적극 활용해서 생산성 높이는데 목표야
- 플로우에서 사용되는 지침과 템플릿을 관리하는 프로젝트야.

## 주요 지침
- ai 결과물에 사용되는 리소스는 아래와 같음
  - prompt/**.md에 지침 저장
  - input/**.md에 사람이 작성하는 파일 저장
  - output/**.md로 결과물 저장
  - template/**.md로 템플릿 저장
- 각 ai 활용 단계에서는 이전 단계에서 작성했던 md 파일들을 참고하여 진행한다.

## 서비스 개발 플로우

### 프로젝트 개요서 작성
1. 사람이 직접 프로젝트 개요서 작성 (template/project_overview.md)
2. ai가 프로젝트 개요서 고도화
   1. input: input/project_overview.md 
   2. output: output/project_overview.md

### 기능 명세서 작성
1. AI가 프로젝트 개요서보고 기능 명세서 작성 / 피드백
   1. input: output/project_overview.md 
   2. output: output/feature.md

### 디자인 명세
1. AI가 디자인 명세서 작성 / 피드백
   1. input: output/project_overview.md, output/feature.md 
   2. output: output/design.md, figma file

### BE 개발
1. AI가 백엔드 프로젝트 설계 md 작성
   1. input: output/feature.md 
   2. output: output/be_project.md
2. AI가 백엔드 프로젝트 및 프레임워크 개발
   1. input: output/be_project.md
   2. output: be project source code
3. 기능 개발 md 작성
   1. input: output/feature.md
   2. output: output/be_feature.md
4. 기능 개발
   1. input: output/be_feature.md
   2. output: be feature source code

### FE 개발
1. AI가 FE 프로젝트 설계 md 작성
    1. input: output/feature.md
    2. output: output/fe_project.md
2. AI가 FE 프로젝트 및 프레임워크 개발
    1. input: output/fe_project.md
    2. output: fe project source code
3. 기능 개발 md 작성
    1. input: output/feature.md
    2. output: output/fe_feature.md
4. 기능 개발
    1. input: output/fe_feature.md
    2. output: fe feature source code

### QA
사람이 직접 진행

### 배포 단계
github action으로 진행