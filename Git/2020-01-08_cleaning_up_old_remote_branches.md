# Remote 브랜치에서 삭제된 브랜치 참조 제거

작업을 하다가 local 개인 브랜치를 실수로 remote repository에 push를 하게 되었다.
remote에 올려지길 원하지 않았기에 삭제를 했는데, 로컬에서는 remote 브랜치가 삭제된 것을 인지하지 못하고 있었다.

![dangling](https://user-images.githubusercontent.com/16912219/71945581-90e1cb80-320a-11ea-86c0-bac6ecfa2694.png)

remote 브랜치와 모든 브랜치(remote/local) 확인해보았다.  
![git remote branch](https://user-images.githubusercontent.com/16912219/71945578-90493500-320a-11ea-8e8e-cc0070dc1947.png)
![all branch](https://user-images.githubusercontent.com/16912219/71945580-90e1cb80-320a-11ea-886a-3c0a01849519.png)

[git prune](https://git-scm.com/docs/git-remote#Documentation/git-remote.txt-empruneem)을 이용하면 delete된 브랜치 참조를 끊을 수 있다고 나와있다.

![git prune](https://user-images.githubusercontent.com/16912219/71945577-90493500-320a-11ea-901b-55320b98974b.png)
delete된 remote 브랜치 참조를 끊은 모습

다시 remote 브랜치 조회 결과</br>
![git prune result](https://user-images.githubusercontent.com/16912219/71945579-90e1cb80-320a-11ea-9620-d62e08456930.png)