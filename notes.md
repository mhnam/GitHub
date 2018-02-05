# GitHub-test
kim@jongkwangmail.com
mail@jongkwang.com

## 1. Introduction
### Open Source란
공개된 Source Code, 참여(기획, 의도가 함께 논의되고 의사결정이 이루어져야함)와 문서(메뉴얼, 소스코드, 패치)가 동반되어야 함
c.f. (참여가 불가능함) Android, Tizen / (관리가 되지 않음) 공개 SW 대회

### Motivation
한 사람이 모든 사용자 환경에서 test하고, 문서화, 번역을 할 수가 없음.
(개인) 코딩 능력을 검증하기 위함
(기업) 사용자를 늘리기 위함-확산
(구글) white paper으로 시작된 같은 프로젝트, map reduce < hadoop / Bigtable < Hbase / Google Code Search < Sourcegraph / Borg < Docker / TensorFlow (먼저 오픈소스로 만듦)

## 분산관리 시스템: 버전관리 시스템
### 1. 클라이언트 서버 (subversion)
* 서버에서는 저장하고, 컴퓨터(클라이언트)에만 저장함.
* 인터넷이 안되면 작업이 되지 않음.
* Branch도 불가능함.
* 숫자로 관리

### 2. 분산 (git)
* 분산해서 저장함. (여러 군데 모두 저장함)
* 오프라인에서도, commit, branch가 자유로움
* hash (난수)로 순번을 붙임, 단 부모 값을 기록함. - GitHub에서는 7개 값만 작성함.
* Local > stage > repository 의 순서로 commit이 됨. stage는 임시저장소 같은 역할

_c.f._
1) GitHub은 git을 웹으로 서비스하는 것
_e.g._
1) 서울 정보소통광자 행정정보 공개 GitHub.com/seoul-opengov/opengov
2) 백악관 정보 GitHub.com/whitehouse/budgetdata

## 2. GitHub
### Creating GitHub
-gitignore: GitHub에서 버전 관리 하지 않을 것들 — java이면 java라고 할것
-license: MIT

### Pointers
* Origin: GitHub
* Head: 작업중인 파일

### Merge
Developer should manually merge code, then let git to merge by pointer

### Checkout
Using pointers - head - to check codes

### Branch


_c.f._
1) Git w/ CLI is skipped (push and pull using terminal)
2) Refer to [https://git-scm.com/book/ko/v2](https://git-scm.com/book/ko/v2)

## 3. Communication
### Writing: Markdown
#### Motivation
To write documents neatly on GitHub

#### Grammar
1. [http://blog.kalkin7.com/2014/02/05/wordpress-markdown-quickreference-for-koreans](http://blog.kalkin7.com/2014/02/05/wordpress-markdown-quickreference-for-koreans)

2. [https://gist.github.com/ihoneymon/652be052a0727ad59601](https://gist.github.com/ihoneymon/652be052a0727ad59601)

#### Editor
1. [Marxico](https://marxi.co/#notebook-tags)

2. [Haroopad](http://pad.haroopress.com)

### Draw: Mockup Tool

## 4.
### Issues
kind of board to share followings:

- 질문 및 요구사항들을 올려 놓는 곳
- 담당자
- Label
- Milestones

_e.g._
1. [AXISJ](https://github.com/thomasJang/axisj/issues)

2. [TensorFlow(1)](https://github.com/tensorflow/tensorflow/issues)

3. [TensorFlow(2)](https://github.com/tensorflow/tensorflow/issues/12059)

4. [php29/stack](https://github.com/php79/stack/issues)

### Pull Request

### Merge

### Conflict

### Fork
