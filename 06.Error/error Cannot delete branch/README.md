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

이 부분에서는 이어서 계속 작성을 해보겠다.