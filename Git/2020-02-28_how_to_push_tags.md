# Git Tag Push하기

일반적으로 Tag는 release 버전 관리를 위해 달아놓는 꼬리표이다. _~~(이곳은 아니지만..)~~_

Lightweight나 annotated 태그를 만들었다면 Remote branch에 push를 해줘야 반영이 된다.
<br>`git push origin <tagName>` 명령어로 Push할 수 있다.

```bash
$ git push origin v1.5
Counting objects: 14, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (14/14), 2.05 KiB | 0 bytes/s, done.
Total 14 (delta 3), reused 0 (delta 0)
To git@github.com:schacon/simplegit.git
 * [new tag]         v1.5 -> v1.5
```