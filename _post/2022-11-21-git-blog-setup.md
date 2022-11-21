---
layout: post
title:  "git blog setup"
---



# git hub blog 만들기



- git hub login
- Repositories $\rightarrow$ New $\rightarrow$ Repository name : sjkimq.github.io $\rightarrow$ Public $\rightarrow$ Add a README file $\rightarrow$ Create repository
- Code $\rightarrow$ "1 branch" $\rightarrow$ New branch $\rightarrow$ Branch name : gh-pages $\rightarrow$ Create branch
- sjkimq.github.io 를 로컬에 복사
- git hub theme 다운로드
  - https://github.com/topics/jekyll-theme 이동
  - mmistakes/minimal-mistakes theme 이동
  - Code $\rightarrow$ Download ZIP $\rightarrow$ 로컬에 다운로드 후 minimal-mistakes-master.zip 압축 풀기
  - minimal-mistakes-master 폴더 내부 모든 파일을 sjkimq.github.io 에 복사
- git hub desktop에서 Current Branch를 gh-pages 로 변경 후 Commit to gh-pages 클릭 $\rightarrow$ Push origin
- Create Pull Request
- git hub web 에서
  - Open a pull request
    - base : main $\leftarrow$ compare : gh-pages
    - "minimal-mistakes-master updated" 본문에 코멘트
  - Create pull request
  - Merge pull request
  - Confirm merge



- _config.yml 수정 (꼭 해야되는지 모르겠음) [1]
  - url 수정
    - url                      : "https://sjkimq.github.io"
  - git 에 update



- post 만들기 [1]
  - 로컬에 sjkimq.github.io 하위에 _post 폴더 생성
  - "2022-11-21-git-blog-setup.md" 파일을 _post 하위에 복사
  - https://jekyllrb.com/docs/posts/ 이동
  - --- layout: post title:  "Welcome to Jekyll!" --- 를 본문에 복사
  - git 에 update



- jupyter notebook을 blog로 발행 [1]
  - File $\rightarrow$ Download as $\rightarrow$ Markdown(.md) $\rightarrow$ markdown file로 download가 완료 됨
  - download 된 markdown 파일명 수정 (년-월-일-제목.md)
  - git 에 update





### References

[1] 깃헙(GitHub) 블로그 10분안에 완성하기 (https://youtu.be/ACzFIAOsfpM)

