# Tag 삭제 방법

간혹 Tag를 삭제를 하고 원격 저장소에 이를 반영해야 할 때가 있다.

```
git tag -d <tag_name>
```

위와 같이 하면 로컬에서 tag가 제거된 것을 확인할 수 있다.
<br>그리고 로컬에서 삭제된 tag를 원격 저장소에 적용하려면 push를 해줘야 한다.


```
git push origin :<tag_name>
```
또는
```
git push origin :refs/tags/<tag_name>
```

원격 저장소에 변경 내역을 적용했다면 `git pull --prune --tags`를 적용해주자. 협업하는 동료들이 굳이 삭제된 tag를 갖고 있을 필요가 없을테니.

<details>
  <summary>
    Tip: Tag 수정 방법
  </summary>
찾아보니까 지우고 새로 만들라더라...
</detilas>