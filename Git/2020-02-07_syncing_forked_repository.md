# Fork된 repository sync하기

블로그로 Gatsby starter를 쓰면서 버전업 되면 어떻게 sync를 맞춰야 할지 찾아보았다.

내 블로그가 올라가 있는 repository를 확인하기 위해서 아래와 같이 remote의 url를 조회해봤다.
```
$ git remote -v
> origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
> origin  https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
```

기존 remote 정보에 새롭게 sync할 remote repository를 등록해준다. (starter의 원본 repository 주소)

```
$ git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git
```

다시 remote의 상세 정보를 조회하면 아래와 같다.

```
$ git remote -v
> origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (fetch)
> origin    https://github.com/YOUR_USERNAME/YOUR_FORK.git (push)
> upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (fetch)
> upstream  https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git (push)
```

Upstream repository에서 fetch해와서 upstream/master에 저장해둔다.
(fetch와 pull은 둘 다 변경된 것을 가져오지만, fetch는 갖고 오기만 하고 pull은 merge까지 해준다. - [fetch와 pull의 차이점](https://stackoverflow.com/a/292359))
```
$ git fetch upstream
> remote: Counting objects: 75, done.
> remote: Compressing objects: 100% (53/53), done.
> remote: Total 62 (delta 27), reused 44 (delta 9)
> Unpacking objects: 100% (62/62), done.
> From https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY
>  * [new branch]      master     -> upstream/master
```

Local의 master 브랜치로 checkout 한 후, fetch해서 갖고 온 upstream/master를 머지한다. 이 때 발생하는 merge conflict를 해결해야 한다.
```
$ git checkout master
> Switched to branch 'master'
```
```
$ git merge upstream/master
> Updating a422352..5fdff0f
> Fast-forward
>  README                    |    9 -------
>  README.md                 |    7 ++++++
>  2 files changed, 7 insertions(+), 9 deletions(-)
>  delete mode 100644 README
>  create mode 100644 README.md
```

나는 merge를 할 때 `fatal: refusing to merge unrelated histories` 에러가 나서 `--allow-unrelated-histories` 옵션을 주어야 했다.



---
[참조]
- [Configuring a remote for a fork](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork)
- [Syncing a fork](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork)