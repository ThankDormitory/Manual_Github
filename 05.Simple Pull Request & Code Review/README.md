# Pull Request & Code review

# Window & Ubuntu

**<처음 PRCR>**

- git clone **포크뜬 본인의 깃허브 주소**
- git remote add **real-blog** **원본 깃허브 주소**
- git checkout -b **운영체제**
- git add .
- git commit -m **"할말"**
- git push origin **운영체제**
- 그후 웹사이트에서 PR 작업을 진행하면 된다.

**<최신 원본 저장소에 있는걸 포크뜬 깃허브 주소로 옮기기>**

- git fetch **real-blog**
- git checkout main
- git merge **real-blog/main**
- git push origin main

**<한번하고 나면 그냥 연속해서>**

- git pull (맨처음 포크 뜬 곳에서 pull하기)
- git checkout **운영체제**
- git add .
- git commit -m **"할말"**
- git push origin **운영체제**
- git fetch **real-blog**
- git checkout main
- git merge **real-blog/main**
- git push origin main

**<요약>**

- git pull 
```
(맨처음 포크 뜬 곳에서 pull하기)
```
- git checkout **운영체제**
- git add .
- git commit -m **"할말"**
- git push origin **운영체제**
- git fetch **real-blog**
- git checkout main
- git merge **real-blog/main**
- git push origin main

# Mac

<처음 PRCR>
- git clone **포크뜬 깃허브 주소**
- git remote add **real-blog** **원본 깃허브 주소**
- git checkout -b **Mac**
- git add .
- git commit -m **"할말"**
- git push origin **운영체제**
....
웹사이트에서 작업진행
...

<최신 원본 저장소에 있는걸 포크뜬 깃허브 주소로 옮기기>

- git fetch **real-blog**
- git checkout master
- git merge **real-blog/master**
- git push origin master

<한번하고 나면 그냥 연속해서>
- git pull **(맨처음 포크 뜬 곳에서 pull하기)**
- git add .
- git commit -m **"할말"**
- git push origin **Mac**
- git fetch **real-blog**
- git checkout master
- git merge **real-blog/master**
- git push origin master