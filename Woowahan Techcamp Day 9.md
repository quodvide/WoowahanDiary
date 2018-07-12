# Woowahan Techcamp Day 9

## 데일리 미팅 (9:00 ~ 9:15)

어제 어땠나?

- 좋았다
- 삽질이 많아서 좋았다. 
- 강의 미션의 반복이라 졸렸다. 
- 짝코딩이 은근 힘들다 

오늘 하루는? 

- 강의 들으면서 하루를 버틴다 

## 호눅스님 강의(9:20 ~ 17:00) - Git 

- **git의 작업공간**은 
	- **Working Directory**(working tree, w.t) : 현재 내 작업하고있는 디렉토리
	- **Stage(Index)** : .git파일 내에 존재하고 있는 공간. 논리적으로는 존재하지만 물리적으로는 그냥 파일이다.
	- **Local Repository** : 오프라인 환경에서도 commit할 수 있는 내 컴퓨터의 저장소
	- **Remote Repository** : 온라인 환경에서 push할 수 있는 온라인상의 저장소 
- **git init [DIR]** : 현재 작업디렉토리를 로컬 레파지토리로 만들겠다. 
	- .git 생성 -> 로컬 레파지토리. 안에 깃과 관련된 파일이 들어있다. 
- **git clone <저장소>** [디렉토리/저장소이름, defalult는 깃레포이름]  
	- URL(http://)
	- URN(ssh://)
	- 디렉토리(깃인 디렉토리)
- **git add <파일명>** : 특정 파일을 stage에 올린다
- **git commit** : git의 유일한 객체이다. 나중에 아무때나 이 상태로 되돌릴수 있게 하기 위해 이 시점의 SnapShot을 저장한다. 
	- Commit은 항상 부모의 포인터를 가지고있다. 
	- Commit을하면 새로운 Commit이 생기고 헤드를 부모로 가르키고 헤드가 가르키고있는 브랜치와 헤드를 새로운 커밋으로 이동, detached commit일때는 헤드만 이동한다. 
	- Commit은 스테이지에 있는 파일만 올린다.
	- Commit의 기준은 보통 기능단위이고, 팀원간의 상의로 Convention을 만들어야 한다. 
	- Commit의 id는 절대 같을 수 없다. 
- **git push [원격저장소(생략시UpStream)] [브랜치]** : 로컬저장소의 커밋을 원격저장소에 보내는것 => 원격저장소에 없는 해당 브랜치의 commit 히스토리만 올린다(없는거 전부) 
- **git pull** : 로컬저장소에없는 commit들을(전부) 리모트저장소에서 가져와서(fetch) 내 commit과 merge함(fetch + merge) 
- **git fetch [저장소] [브랜치]** : 로컬저장소에 없는 commit들을 전부 가져온다. 
- **git status** : stage, w.t의 차이점을 우리에게 가르쳐준다. 
	- status가 깨끗한상태 -> w.t, stage, commit의 상태가 같다
- **git branch <브랜치>** : 브랜치를 생성한다.
	- branch는 결국 아무것도 아니고 commit의 reference일뿐이다 
	- **git branch -d(D) <브랜치>** : 브랜치 삭제(D옵션 : 강제 삭제)
	- git의 태그 : 보통 프로그램을 release할때 version을 기록하기위해 쓰인다. 갱신은 불가능하다.
- **head** : 현재 작업중인 브랜치의 reference
	- 현재 브랜치가 어딘지 아는것 -> head를 보고 안다.
- **git checkout <commit or 브랜치>** -> head를 특정 commit 혹은 브랜치로 이동시키고 그 시점에 저장한걸 로드한다. (로컬저장소의 특정 commit을 stage, w.t에 넣는다)  - **detached commit** : 브랜치 없이 헤드만으로 커밋하는것(좋지 않다.)
- **git reflog** : commit의 reference 목록을 보여준다.
- **git reset** : 커밋을 뒤로 돌리고 싶을때 사용한다
	- soft : stage, w.t안건드린다. 단지 헤드만 특정 커밋으로 이동만한다 
	- hard : stage, w.t모두 리셋한다 
	- mixed : stage를 리셋하지만 w.t는 안건드린다 
- **git rm —cached [파일명]** : stage의 파일 삭제 
- **git stash** : stash라고하는 별도공간에 w.t를 그대로 옮긴다. 다른 작업 후 그대로 복구할 수 있기 때문에 특정 브랜치에서 기능구현도중 다른 브랜치로 급하게 이동해야 할 상황에 자주 쓰인다.
	- **git stash pop** : stash의 맨위 snapshot을 꺼내오고, stash에서는 제거한다.
	- stash파일을 여러개 만들거나 pop으로 제거 시키지않고 그냥 꺼내올수도있다.
- git hash-object [파일명] = 메타정보X, 무조건 파일 내용으로만 SHA1 해쉬값을 반환한다. 
- Add 를 하면 해쉬값이 .git /object에 생성된다.
- git cat-file -t [파일명] : 파일이 무슨 종류인지 알려준다.
	- Blob => Binary large object 바이너리파일
- git cat-file 파일종류 [파일명] : 파일의 내용을 보여준다. 
- git rebase : 변경내용을 마스터 아래에 한줄로 만들어준다. 깔끔해보인다는 장점이 있으나 충돌가능성이 있다.
- git merge : commit이력을 잃어버리지 않고 다 남길 수 있다. 마찬가지로 충돌을 해결해야 하고, rebase 보다는 조금 복잡한 commit history로 보여질 수 있다.
	- Reset —hard 정말 안좋다, Revert는 보존 + 돌아갈수있다 그러나 충돌을 해결해야 한다. 
	- branch후 merge나 rebase가 가장 편하며 좋다.(충돌을 해결해야 하긴 한다.)
 

 