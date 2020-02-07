# fatal: refusing to merge unrelated histories 해결기

[포크된 repository sync](./2020-02-07_syncing_forked_repository.md)를 하다가 위와 같은 에러가 발생했다.

Merge를 하려면 공통 commit을 기준으로 서로 다른 commit들을 merge해야하는데 공통 commit이 존재하지 않아서 병합할 수 없어서 나는 에러이다. `--allow-unrelated-histories` 옵션을 주면 정상적으로 병합이 된다.

---
[참조]
- [Git refusing to merge unrelated histories on rebase](https://stackoverflow.com/a/37938036)