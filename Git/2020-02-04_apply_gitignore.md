# .gitignore 적용하기

이미 존재하던 .gitignore 파일에 IDE 세팅 폴더인 .vscode, .idea 폴더를 제외시키기 위해 추가를 했다.

```gitignore
# IDE settings
.vscode/
.idea/
```

이후 이미 push 된 폴더들과 tracked 되는 파일들을 제거할 필요가 있었다.

```bash
git rm -r --cached .
git add .
git commit -m "Apply .gitignore"
git push
```

이렇게 하면 기존에 push 된 파일 또는 폴더들도 제외되게 된다.