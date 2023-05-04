# Git과 GitHub

## Git이란?

### 버전 관리 시스템(Version Control System, VCS)의 하나이다

#### 말그대로 '버전'을 관리할 수 있는 시스템이다. 수정 사항이나, 업데이드 사항 등을 그떄 그때 바로 반영 할 수있도록 하는 시스템을 말한다.

## 버전 관리 시스템이란?

### 버전 관리 시스템(VCS)은 파일 내 변화를 시간의 흐름에 따라 기록했다가, 이후 필요한 상황에서 그 파일을 꺼내올수 있는 시스템을 말한다.

#### Git은 분산 버전 관리 시스템이다.

#### VCS의 종류

- 로컬 버전 관리 시스템(Local VCS)
- 중앙 집중식 버전 관리 시스템(Centralized VCS - CVCS)
- 분산 버전 관리 시스템(Distributed VSC)
<hr>

## GitHub란?

### 분산 버전 관리 시스템인 Git을 기반으로 소스 코드를 호스팅 하고, 협업 지원 기능들을 지원하는 웹서비스이다.

<hr>

## Git과 GitHub의 차이점

#### Git은 개인 컴퓨터에서 돌아가는 Version Control System이다. Git을 사용하기 위해서는 개인 계정을 등록할 필요도 없으며 인터넷을 연결할 필요도 없다. 반대로 GitHub는 회사에서 서비스하고 있는 서버에 올라간 Git 이기 떄문에 사용하기 위해 개인 계정을 등록해야 하며, 인터넷에 연결되어야 사용할수 있다.

<hr>

## Repository란?

#### 저장소(repository)란 말그대로 파일이나 폴더를 저장해 두는 곳이다, 그런데 Git 저장소(repository)가 제공하는 좋은 점 중 하나는 파일이 변경 이력 별로 구분되어 저장된다는 점입니다. 비슷한 파일이라도 실제 내용 일부 문구가 서로 다르면 다른 파일로 인식하기 때문에 파일을 변경 사항 별로 구분해 저장할 수 있다.

#### Git은 원격 저장소와 로컬 저장소 두 종류의 저장소를 제공한다.

- 원격 저장소(Remote Repository): 파일이 원격 저장소 전용 서버에서 관리되며 여러 사람이 볼수 있는 저장소이다
- 로컬 저장소(Local Repository): 내 PC에 파일이 저장되는 개인 전용 저장소이다

### git init

#### git init은 새로운 Git 저장소(repository)를 생성할 때 사용하는 Git 명령어 이다.

```
$ git init
```

### git clone

#### git clone은 깃허브 repository에 있는 파일을 내 컴퓨터로 복제하는 명령어이다. repository를 복사해오기 위해서는 repository의 주소를 알아야 한다.

```
$ git clone [repository 주소]
```

### git commit

#### git commit은 코드의 변화를 기록하는 명령어이다.

```
$ git commit -m "커밋 메세지"
```

### git push

#### git push는 git commit을 통해 로컬저장소에 기록을 남긴것을 원격저장소로 전송을 하는 명령어이다.

```
$ git push [저장소 이름] [브랜치 이름]
```

### git pull

#### git pull은 원격 저장소에 있는 프로젝트 내용을 가져와 현재 브랜치와 병합을 해주는 명령어 이다.

```
$ git pull [원격 저장소 이름] [브랜치 이름]
```

### git status

#### git status는 파일의 상태를 확인할 수 있는 명령어이다.

```
$ git status
```

### git log

#### git log는 커밋한 이력을 상세 조회를 할 수 있는 명령어이다.

```
$ git log
```

### git add

#### git add는 변경 내용을 스테이징 영역(staging area)에 추가하기 위해서 사용하는 명령어이다.

```
$ git add
```

### git reset

#### git reset은 커밋을 취소하는 명령어이다.

```
$ git reset [옵션] [돌아가고 싶은 커밋]
```

### git fetch

#### git fetch는 원격 저장소의 내용을 가져온다 하지만 git pull처럼 현재 브랜치화 병합은 하지 않는다

```
$ git fetch
```
