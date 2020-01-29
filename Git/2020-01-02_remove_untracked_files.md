# Untracked files 삭제
오전에 작업하던 것들이 git untracked files로 쌓여 있어 삭제 방법을 찾아보았다.
ember-typescript를 설치하면서 생성된 폴더 및 파일이었다. 현재 프로젝트에서 typescript를 사용할 수 있을까 싶어서 설치했었는데, 자체적으로 트윅된 프레임워크에선 도저히 이용할 수 없었다.

삭제를 하기 전에, 남겨둘 작업들은 stash에 저장해둔 후 진행하였다.

>untracked된 file들 삭제: `git clean -f` <br>
>디렉토리까지 함께 삭제: `git clean -fd`

