# GitHub-test

## Contents
1. [Introduction](#1-introduction)
2. [Intro to GitHub]()
3. [Communication]()
4. [Advanced GitHub Usage]()

## 1. Introduction
### 1-1. What is Open Source?
공개된 Source Code, 참여(기획, 의도가 함께 논의되고 의사결정이 이루어져야함)와 문서(메뉴얼, 소스코드, 패치)가 동반되어야 함
c.f. (참여가 불가능함) Android, Tizen / (관리가 되지 않음) 공개 SW 대회

### 1-2. Why Open Source?
한 사람이 모든 사용자 환경에서 test하고, 문서화, 번역을 할 수가 없음.

* (개인) 코딩 능력을 검증하기 위함
* (기업) 사용자를 늘리기 위함 - 확산
* (구글) white paper로 시작된 같은 프로젝트, map reduce < hadoop / Bigtable < Hbase / Google Code Search < Sourcegraph / Borg < Docker / TensorFlow (먼저 오픈소스로 만듦)

### 1-3. Preliminaries: 분산관리 시스템 (aka 버전관리 시스템)
#### 클라이언트 서버 (subversion)
* 서버에서는 저장하고, 컴퓨터(클라이언트)에만 저장함.
* 인터넷이 안되면 작업이 되지 않음.
* Branch도 불가능함.
* 숫자로 관리

#### 분산 (git)
* 분산해서 저장함. (여러 군데 모두 저장함)
* 오프라인에서도, commit, branch가 자유로움
* hash (난수)로 순번을 붙임, 단 부모 값을 기록함. (GitHub에서는 7개 값만 작성함)
* Local > stage > repository 의 순서로 commit이 됨. stage는 임시저장소 같은 역할 (개발 중에 다른 branch의 개발 상태를 확인해야할 때, 현재 개발 중인 것을 stage에 올린 후 다른 branch의 내용을 실행 시키면, 추가 개발되기 이전의 version으로 확인이 가능함.)

_c.f._
1) GitHub은 git을 웹으로 서비스하는 것.

_e.g._
There are some other examples for usage  
* [서울 정보소통광자 행정정보 공개](http://www.gitHub.com/seoul-opengov/opengov)
* [백악관 정보](http://www.gitHub.com/whitehouse/budgetdata)

## 2. Intro to GitHub
### 2-1. Creating Repository
Things to aware while creating new repository:
* ```gitignore```: GitHub에서 버전 관리 하지 않을 것들 (java면 java라고 할것)
* ```license```: MIT
* create ```README.md```

### 2-2. Pointers
There are some pointers to mark where you are at (aka mark version):

* origin: GitHub
* origin/HEAD: Current GitHub status
* HEAD: Current Local status
* master: Branch

### 2-3. Merge
If there is a ```CONFLICT``` developer must manually merge code (```3-WAY MERGE```). Git will automatically merge between each sides (most case) or saves (refers) their ancestor if there is no such difference between branches (```FAST MERGE```).

### 2-4. Checkout
Rolling back to previous working version by moving  ```HEAD``` pointers

### 2-5. Branch
When developers co-operate a project, there will be various revision from all over the part, then it would be difficult to track the difference between versions and where it starts from. Hence, developers make various branch to control each version's ancestor (aka parent)!

_c.f._
1) Git w/ CLI is skipped (push and pull using terminal)
2) Refer to [https://git-scm.com/book/ko/v2](https://git-scm.com/book/ko/v2)

## 3. Communication
There are two important methods to communicate between developers - writing and drawing

### 3-1. Writing: Markdown
To write documents neatly on GitHub, we need to learn how to write using markdown grammar.

Here are some references for markdown grammar:
* [blog.kalkin7.com](http://blog.kalkin7.com/2014/02/05/wordpress-markdown-quickreference-for-koreans)
* [ihoneymon's GitHub](https://gist.github.com/ihoneymon/652be052a0727ad59601)
* [pdf user guide](https://git-scm.com/book/ko/v2)

There are some editors for markdown documents:
* [Marxico](https://marxi.co/#notebook-tags)
* [Haroopad](http://pad.haroopress.com)

### 3-2. Draw: Mockup Tool
Please refer to this program [Balsamiq](https://balsamiq.com/products/).

## 4. Advanced GitHub Usage
### 4-1. Issues
Issue is a place where other developers can share their thoughts or issues regarding codes on the repository. Moreover, people can ask and answer on the projects on this sub-menu.

_c.f._ There are more functions as follows:
* Label
* Milestones

_e.g._ Here are some good usage examples on issues:
* [AXISJ](https://github.com/thomasJang/axisj/issues)
* [TensorFlow(1)](https://github.com/tensorflow/tensorflow/issues)
* [TensorFlow(2)](https://github.com/tensorflow/tensorflow/issues/12059)
* [php29/stack](https://github.com/php79/stack/issues)

### 4-2. Pull Request
Getting the most latest version from GitHub

_c.f._ Difference between ```PULL``` and ```FETCH``` on Sourcetree program:

* ```FETCH``` is to check the updated files from the origin (mark files that requires pulling action)
* ```PULL``` is to update your client from the origin (real change happens)

### 4-3. Merge
#### Branch
Developer mainly use ```DEVELOP``` and ```MASTER``` branch to keep the ```MASTER``` branch neat.

Depend on its situation, team can make additional branches as follows:
* ```FEATURE``` brach is to let some team member to in charge of specific function/part of the whole code, usually make name as iss## or [name_of_the_feature]-branch
* ```HOT-FIXES``` branch is for URGENT TASK, which should be merge to ```DEVELOP``` branch ASAP to update the urgent issues (usually security issues)
* ```RELEASE``` branch

#### Merge
There are two different kinds of merge:
* ```Fast merge``` happens when branch can be merge directly to the master branch. This merge just saves the address of the branch rather making additional file.
* ```3-way merge``` happens when each branch (master and develop) modified separately so that previous master, latest master, and final develop branch must be referred to merge into one single code.

#### Conflict
When both codes are modified the same line/part of their ancestor from two(or more) files ```Conflict``` occurs.

Hence developer **MUST manually** merge the files and **CLICK '(re)solve' button**, to let GitHub know that the conflict issue is closed.

### 4-4. Fork
To copy the other's repository to your GitHub use ```Fork```. This can be used as following reasons:

1) to see the contribution or importance of the project in developing society.

2) to contribute on other projects. Unless you cannot edit any of the project which you are not committer.

_c.f._

1) Remote pull

This method is used to avoid conflict between original repository and your forked repository. Conflict may occur if you send pull request from your forked repository after the original one is updated.

Add original repository (what you forked) as origin repository (```SourceTree > Setting > Remote > add```). Then your SourceTree would pull the changes from your own repository AND original one when you click ```FETCH``` or ```PULL```. Hence, your local client (aka computer) can download the latest version from the original repository.

### 4-5. Unit test
This procedure is required to verify the code of pull request, before reading the code line by line. This can save your time when you manage a huge Open Source Project where a lot of developer wants to join in.

Following services are useful in terms of unit test:
* ```Travis CI```: build various types of user environment where you can test and build your program
* ```Code Coverage```: calculate the coverage of test case on a whole code, so that you can check how much does the test case can cover the new pull request program.

_c.f._

1) **BE AWARE** to provide **TEST CASE**:

when you add a new function on the project via pull request. This requires additional (kind of) function to call your newly developed function. Otherwise your pull request would be rejected.
