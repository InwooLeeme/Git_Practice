# GitHub를 위한 기초 Git 사용법

1. 시작 전 준비

   #### (1) Git 설치

   - GitHub 사용을 위해 [https://git-scm.com/]에서 깃을 다운 받는다.
   - Windows에선 Git Bash를 통해, mac OS에선 터미널에서 실행.
     - 터미널에서 git --version을 실행해 버젼이 나오면 설치된 것을 알 수 있다.

   #### (2) GitHub 가입

   - ["https://github.com/"]에 가입해서 새로운 Repository를 설정해 줍니다.

2. Git 세팅
   #### (1) 최초 사용자 설정
   - git 설정(user.name & user.email) : **최초1회 설정**
   - user.email은 **Github 아이디**로 작성해야 함.
   ```
   // 터미널에서
   git config --global user.name [사용자이름]
   git config --global user.email [이메일]
   ```
   #### (2) core.autocrlf : 줄바꿈 설정
   운영체제 마다 줄바꿈 설정이 달라지는 것을 자동으로 보완해주는 옵션
   - Windows의 경우 \r(carriage-return)과 \n(line feed)를 모두 포함
   - Windows에서 설정시 true으로 설정.
   - Mac OS의 경우 \n(line feed)만 포함
   - Mac OS에서 설정시 input으로 설정.
   ```
   // 터미널에서
   //Windows
   git config --global core.autocrlf true
   //Mac OS
   git config --global core.autocrlf input
   ```
   #### (3) Git으로 프로젝트 관리 시작 : git init
   - 폴더를 생성하고, Github에 업로드할 파일을 작성.
   - 터미널에서 생성한 폴더가 있는 위치로 이동후 git init명령어를 사용해 git 관리를 시작한다.
   ```
   git init
   ```
   #### (4) git을 제거
   ```
   rm -rf .git
   ```
   #### (5) git의 상태를 조회
   ```
   git status
   ```
   #### (6) commit을 위한 Staging : git add
   ```
   git add [파일 이름]
   ```
   - git add .으로 작성 시 모든 변경사항을 Staging area로 옮긴다.
   - 이 때 .gitignore파일을 추가해서 그 안에 옮기고 싶지 않은 것들의 파일명을 작성하면 Staging area로 옮겨지지 않는다.
   #### 그 외 명령어
   - 파일 비교(working dictory에 있는 것만 표시) : 자세하게 어떤 파일에 어떤 내용이 변경되었는지 표시.
   - q를 눌러서 종료
   ```
   git diff
   ```
   - 파일 비교(staging area에 있는 것 표시)
   ```
   git diff --staged
   ```
   - 버젼 관리 이력 조회
   ```
   git log
   ```
   - 폴더명 변경
   ```
   git mv 바꿀파일명 바뀐파일명
   ```
   - 파일,폴더 삭제
   ```
   git rm -rf 파일명 = 원격, 로컬 저장소에서 삭제
   git rm -r --cached 파일명 = 원격 저장소에서 삭제
   ```
3. 커밋하기
   ```
   git commit
   ```
   - commit은 history이기 때문에 만들고자하는 각각의 기능별로, 작은 단위로, 의미있는 커밋을 만들어서 커밋을 하는게 좋다.
   - 보통 커밋의 메세지는 현재형으로 그리고 동사로 만들어진다.
   - Commit을 할 때 고친 내용**만** 해당하는 커밋을 해야하지 다른 부가적인 내용도 커밋을 하면 history를 보는데 혼동이 오기 때문에 해당하는 부분만 커밋을 하는게 좋다.
