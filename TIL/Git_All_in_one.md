# Git 역사 및 배경 지식

- `UNIX` : 대형 컴퓨터를 위한 OS
  - 리눅스 토발즈 : 개인용 컴퓨터에 맞는 OS `Linux` 개발
  - Linux는 `GNU (Linux 철학) == GPL (GNU의 실체) `
    - 누구에게나 공개
    - 단 `GPL (General Public Licence)` 의무 -> 부모 소프트웨어 따라 자식 소프트웨어도 오픈
    - 수 많은 개발자 -> 오픈소스 Linux를 협업 개발
      - 협업이 비효율적
        - `Bitkeepr` 상용 (`DVCS : 분산 버전 관리 시스템`개념 등장)
        - 기존의 `Bitkeeper`가 유료화를 하려하자 리눅스 토발즈가 upgrade하여 `Git` 개발
- Git bash (shell)은 `Linux commad` 를 따름



# GitHub

- `Hub` : 우주의 중심
- `GitHub`는 모든 개발자의 중심, `클라우드 저장소`
- GPL이 아닌 `MIT licence`를 따름 -> 2차 소스코드에 대한 공개 의무 X



# 버전 관리 시스템

1. 기존 파일 관리
   - 파일(또는 프로젝트)관리를 위해 전체 복사, 백업 파일을 만들어 따로 관리를 해야함
   - 시간, 용량의 비효율적 관리와 바이러스에 대한 취약점

2. VCS
   - fil에 대한 DB생성하여 버전 관리, 수정할 때 마다 `수정 내용`에 대해서만 저장 => 효율적인 메모리 관리
   - 바이러스에 대해서는 여전히 취약함, 협업 불가 (ONLY Local)

3. CVCS 
   - VCS + 협업
     - 끝점 (end point) 만 반영, loca은 history에 대한 정보 공유 X
       - 협업시 신경써야 할 요소가 많음
   - 중앙 서버를 연결하여 협업 진행
     - 중앙 서버에 문제가 있을 시 심각한 피해
4. `DVCS (Git)`
   - local에서도 histroy를 모두 공유하여 CVCS의 단점을 모두 보완



# Git 3가지 영역

- `Working directory` : 작업 공간
  - Git은 변경 감지
- `Staging Area` : 인덱스 영역으로 tree 목차를 가지고 있음
  - 변경이 감지된 파일들을 staging area에 올림 (`snapshot`으로 관리)
  - file(BLOB) -> tree(Folder)에 연결됨
  - tree의 확장으로 관리
  - backup log가 있어 모든 내역 복구 가능
- `Local Repository` : 헤더 영역
  - 영구 기록하여 버전(commit)으로 관리
- 40자의 hash 값으로 참조하여 관리 => 효율적인 메모리 관리



# Branch 

- commit -> `master(main) branch` 생성
- main branch의 작업에서 새롭거나 추가적인 작업을 할 때 branch 활용
- `branch` -> `work` -> `merge` (3-way merge / fast-forward merge)

- `Branch pointer`
  - 실제 줄기 모양의 branch가 생기는 것이 아니라 `branch pointer`가 생기고 이동