# Git 폴더 이름 변경

처음 TIL을 만들 때 주제에 대한 폴더들을 소문자로 적었었다. 딱히 문제는 없었지만, 폴더가 주제를 묶는 단위이기에 첫 글자는 대문자로 하는게 보기에 적절하다 느꼈다.

그래서 폴더 이름을 터미널에서 git에서 Git으로 바꿔주었다.

하지만, git에서는 Git이나 git이나 같은 것으로 인지하는지 변화를 감지하지 못했다.

[여기](https://stackoverflow.com/questions/6899582/i-change-the-capitalization-of-a-directory-and-git-doesnt-seem-to-pick-up-on-it)를 보면 나와 같은 이슈를 겪는 사람을 찾을 수 있었다. 원인은 git 설정에서 case sensitive에 관해 무시하도록 설정되어 있기 때문이었다.

`git config core.ignorecase false`

위와 같은 설정을 하면 git에서 case sensitive하게 감지할 것이다.


```
$ git mv aaa tmpAAA
$ git mv tmpAAA AAA
```

git의 global 설정을 변경하기 전에 위와 같은 방법으로 임시 폴더로 이름을 변경 후, 다시 바꾸는 방법을 이용해서 문제를 해결했다.

근본적으로는 config를 변경해서 case sensitive 하게 만드는 것이 낫다고 생각한다.