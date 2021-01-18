# There is no tracking information for the current branch.

깃 허브에서 병합 작업을 하고자 할 때에 남이 올린 코드를 먼저 다운 받아 작업을 수행하려고 한다.

그래서 `git pull` 를 하려고 하는데 이런 오류 메시지가 나온다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git pull
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (8/8), done.
remote: Total 12 (delta 5), reused 7 (delta 3), pack-reused 0
Unpacking objects: 100% (12/12), 2.73 KiB | 4.00 KiB/s, done.
From https://github.com/GloryKim/Practice_How_to_use_Github
   b1cf96c..662f40c  Glory      -> origin/Glory
   130b46c..a070f1b  main       -> origin/main
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=<remote>/<branch> Glory

C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>
```

이게 뭔지 하고 찾아 보았는데 브랜치가 이전에 있던 과거의 브랜치인 상태에서 다운 받고자 하니 문제가 발생 했었다.

그래서 브랜치가 현 상황으로 어떤지를 확인해 볼려고 했다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git branch
* Glory
  main
```

내 이름인 Glory로 되어 있었으며 이걸 main으로 바꿔 준다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git checkout main
Switched to branch 'main'
Your branch is behind 'origin/main' by 6 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>
```

그 후 다시 `git pull`를 해보니 다음처럼 정상적으로 완료가 되었다.

```jsx
C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>git pull
Updating 130b46c..a070f1b
Fast-forward
 .../Pull Request & Code review.md                  | 101 +++++++++++++++++++++
 .../README.md"                                     |  12 +++
 2 files changed, 113 insertions(+)
 create mode 100644 05.Pull Request & Code Review/Pull Request & Code review.md
 create mode 100644 "Issue \352\264\200\353\246\254\355\225\230\352\270\260/README.md"

C:\Users\yklov\Desktop\(Github)\Practice_How_to_use_Github>
```

간단한 해결!