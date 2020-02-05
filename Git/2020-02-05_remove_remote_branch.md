# Remote branch 삭제하기

Remote에 있는 branch를 삭제할 일이 있었는데 예전에 찾아봤던 것을 정리해본다.
stackoverflow에 있는 [답변](https://stackoverflow.com/a/2003515)에 잘 정리되어 있다.

```
$ git push -d <remote_name> <branch_name>
$ git branch -d <branch_name>
$ git fetch --all --prune
```