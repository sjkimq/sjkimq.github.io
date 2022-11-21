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
  - 로컬에 sjkimq.github.io 하위에 _posts 폴더 생성
  - "2022-11-21-git-blog-setup.md" 파일을 _posts 하위에 복사
  - https://jekyllrb.com/docs/posts/ 이동
  - --- layout: post title:  "Welcome to Jekyll!" --- 를 본문에 복사
  - git 에 update



- jupyter notebook을 blog로 발행 [1]
  - File $\rightarrow$ Download as $\rightarrow$ Markdown(.md) $\rightarrow$ markdown file로 download가 완료 됨
  - download 된 markdown 파일명 수정 (년-월-일-제목.md)
  - git 에 update



## commit log

- md 파일 수정 $\rightarrow$ 저장
- git hub desktop
  - commit name 입력 $\rightarrow$ Commit to gh-pages $\rightarrow$ Push origin
- github
  - Repository 에 와서 commits 을 눌러보면 commit한 로그가 보인다
  - Repository 에 와서 Pull request 해주면 된다
  - 



### References

[1] 깃헙(GitHub) 블로그 10분안에 완성하기 (https://youtu.be/ACzFIAOsfpM)

[2] EP01. 개발환경 설치하기 (https://youtu.be/--MMmHbSH9k)

[3] EP02. 이미지 매우 간단하게 추가하기 (https://youtu.be/1UEOWcKcVdk)

[4] EP03. 업데이트 내역을 실시간 확인하기!! (로컬 개발환경 설정방법) (https://youtu.be/0TeHUqSAb6Q)

[5] EP04. 블로그 설정 매우 쉽게 변경하기 - NO코딩! (config.yml 활용) (https://youtu.be/c-h3XcDjHtQ)

[6] EP05. 댓글 & 구글 애널리틱스 추가하기 (https://youtu.be/anXaW9xhgcU)

[7] EP06. 테마변경, SNS 링크 삽입, Pagination 설정 (https://youtu.be/Wi1W3hpfvZc)

[8] EP07. 카테고리 기능, [#태그](https://www.youtube.com/hashtag/태그) 기능 추가하기 (https://youtu.be/3UOh0rKlxjg)

[9] EP08. 글 목차, 404 페이지 에러 구현 (https://youtu.be/OoeGqYu8JFQ)

[10] EP09. 구글, 네이버 검색엔진 등록하기 (https://youtu.be/OxRZrg0u6h4)

[11] EP10. 블로그 내 글 검색기능 추가하기 (https://youtu.be/AONVKTeeaWY)

[12] EP11. 블로그에 설정된 폰트(글씨체) 변경하기 (https://youtu.be/k7DjQ1JF9rY)

[13] EP12. 공지사항(Notice), 버튼, YouTube 영상 추가하기 (https://youtu.be/q0P3TSoVNDM)

[14] EP13. (번외편) 깃헙 커밋 로그에 업데이트가 안된다면? (https://youtu.be/Z053Qn8LJyk)











