# service generator

## project management
- 문서 md로 통일
- 각 단계별 내용은 모든 ai가 접근할수있게 관리 (프로젝트 소스코드 내)
- 피드백받고 진행하니까 버전관리는 필수일듯

1. asdf
   1. asdf

## project flow
1. 아이디어 선정
    1. 프로젝트 개요서 작성
        1. output: project.md
2. 기능 명세 단계
    1. 기능 명세서 작성
        1. input: project.md
        2. prompt:
        3. tool: LLM
        4. output: spec.md
3. 디자인 명세 단계
    1. UI 명세서 작성
        1. input: project.md, spec.md
        2. prompt:
        3. tool: figma make
        4. output: figma file + design.md
4. BE 개발 단계
    1. 프로젝트 설계 md 작성
        1. input: spec.md
        2. prompt:
        3. tool: LLM
        4. output: be-outline-framework.md
    2. 프로젝트 설계
        1. input: be-outline-framework.md
        2. prompt:
        3. tool: coding agent
        4. output: source code
    3. 기능 개발 md 작성
        1. input: spec.md
        2. prompt:
        3. tool: LLM
        4. output: be-outline-spec-01.md
    4. 기능 단위 개발
        1. input: be-outline-spec-01.md
        2. prompt:
        3. tool: coding agent
        4. output: source code
5. FE 개발 단계
    1. 프로젝트 설계 md 작성
        1. input: spec.md, design.md
        2. prompt:
        3. tool: LLM
        4. output: fe-outline-framework.md
    2. 프로젝트 설계
        1. input: fe-outline-framework.md
        2. prompt:
        3. tool: coding agent
        4. output: source code
    3. 기능 개발 md 작성
        1. input: spec.md, design.md
        2. prompt:
        3. tool: LLM
        4. output: fe-outline-spec-01.md
    4. 기능 단위 개발
        1. input: fe-outline-spec-01.md
        2. prompt:
        3. tool: coding agent
        4. output: source code
6. QA 단계
    1. 일단 직접
7. 배포 단계
    1. github action으로 자동화
