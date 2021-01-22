# error: Cannot delete branch

어느날 브렌치를 삭제하려고 했는데, 이런 메시지가 나왔다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git branch -d Glory
error: Cannot delete branch 'Glory' checked out at 'C:/Users/yklov/Desktop/(Github)/Practice_How_to_use_Github'

C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>
```

보니깐 이게 소문자 d 가 아닌 대문자 D로 해야한다고 해서 한번 정정해서 코드를 입력했다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git branch -D Glory
error: Cannot delete branch 'Glory' checked out at 'C:/Users/yklov/Desktop/(Github)/Practice_How_to_use_Github'

C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>
```

똑같은 오류 메시지가 나와서 한번 찾아보니 현재 상태가 Glory인데 Glory를 지울려고 하닌 오류가 발생한것이다. 즉 이미 쓰고있는 중인데 그걸 반강제로 지울려고 하다보니 안된것!

그래서 main으로 branch를 정정해서  다음처럼 진행하였다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
```

그리고 브랜치를 지워 보았다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git branch -d Glory
warning: deleting branch 'Glory' that has been merged to
         'refs/remotes/origin/Glory', but not yet merged to HEAD.
Deleted branch Glory (was 20646cf).
```

그런데 파일 보니 이전에 올려뒀던 파일이 전부 날라갔다..

알고보니 코드를 먼저 병합을 하고나서 진행을 했어야 했던것 ...

요약하면 깃허브 PR 시나리오는 다음과 같다.

1.내가 맨 처음 저장소를 저장한다.

```go
git clone https://github.com/GloryKim/GloryKim.git
```

2.그 다음 cd 명령어를 하고 깃 브랜치를 만든다.

```go
cd GloryKim
git checkout -b Abranch //Abranch에 내가 원하는 브랜치 이름을 입력!
```

3.소스코드 바꾸고 git에 push

```go
git add .
git commit -m "어디어디무슨코드 수정했어요"
git push origin Abranch
```

4.(중요)**사이트에서 PR 승인 시키고** branch를 변경을 해야한다. (main으로 추천)

```go
git branch main
```

5.그다음 이전 브랜치를 지운다 그러면 수정했었던 파일들은 다 사라지고 → 사라진걸 확인 후 git pull로 해서 깃허브에 있는 원본 파일을 복원해서 끌어온다. 그러면 끝

```go
git branch -D Abranch
(파일 사라지는거 확인 후)
git pull
```
