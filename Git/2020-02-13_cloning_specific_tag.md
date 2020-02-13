# 특정 tag clone 하기

[Notable](https://github.com/notable/notable)은 Electron / React로 만들어진 Markdown 노트 앱이다. 1.5.1버전까지는 오픈소스 기반이었다. 이후 버전부터는 개발자가 Full-time으로 개발하기에 더 이상 오픈소스가 아니게 됐다고 한다. ([Link](https://github.com/notable/notable/blob/master/SOURCE_CODE.md))

때문에 소스를 보기 위해서는 v1.5.1로 [tag](https://git-scm.com/docs/git-tag)된 것을 봐야 한다.

![tagged source](https://user-images.githubusercontent.com/16912219/74405257-024b1480-4e70-11ea-8845-fcf2f7292cdb.png)

Branch만 알았지 tag라는 존재는 알지 못했어서 아래와 같이 했다가 당황했다.

```
$ git clone https://github.com/notable/notable.git
Cloning into 'notable'...
remote: Enumerating objects: 4413, done.
Rremote: Total 4413 (delta 0), reused 0 (delta 0), pack-reused 4413                                      76 MiB | 3.83 MiB/s
Receiving objects: 100% (4413/4413), 8.73 MiB | 5.10 MiB/s, done.
Resolving deltas: 100% (2844/2844), done.
```

```
$ git checkout -b v1.5.1
Switched to a new branch 'v1.5.1'
```

Remote의 Branch는 `master`와 `atom-watcher` 밖에 없기 때문에 위와 같이 하면 안된다.


역시 [stackoverflow](https://stackoverflow.com/a/792027)에 답이 있었다.

```
$ git clone <repo_url>
$ git checkout tags/<tag_name>
$ git checkout tags/<tag_name> -b <branch_name>
```

아래와 같이 한다면 한 번에 가능하다. ([Link](https://stackoverflow.com/questions/20280726/how-to-git-clone-a-specific-tag/21699307#21699307))
```
git clone --branch <tag_name> <repo_url>
```
