---
layout: post
title: git blog latex 적용
categories: git-blog
tag: [latex, blog]
---



## git hub blog latex [5]

- _config.yml 파일의 마크다운 엔진 변경 [9], [5]

  - 마크다운 엔진을 kramdown로 세팅할 것. kramdown의 math blocks가 $$처리를 알아서 해준다. [6]

  - _config.yml 파일 내 아래 내용(default 값)
  
    ```md
    # Conversion
    markdown: kramdown
    highlighter: rouge
    lsi: false
    excerpt_separator: "\n\n"
    incremental: false
    
    
    # Markdown Processing
    kramdown:
      input: GFM
      hard_wrap: false
      auto_ids: true
      footnote_nr: 1
      entity_output: as_char
      toc_levels: 1..6
      smart_quotes: lsquo,rsquo,ldquo,rdquo
      enable_coderay: false
    ```

- _includes 폴더 하위에 mathjax_support.html 파일을 만들고 다음 내용을 추가한다.[9]

  ```html
  <script type="text/javascript">
    window.MathJax = {
   tex: {
     packages: ['base', 'ams']
   },
   loader: {
     load: ['ui/menu', '[tex]/ams']
   },
   startup: {
     ready() {
       MathJax.startup.defaultReady();
       const Macro = MathJax._.input.tex.Symbol.Macro;
       const MapHandler = MathJax._.input.tex.MapHandler.MapHandler;
       const Array = MathJax._.input.tex.ams.AmsMethods.default.Array;
       const env = new Macro('psmallmatrix', Array, [null, '(', ')', 'c', '.333em', '.2em', 'S', 1]);
       MapHandler.getMap('AMSmath-environment').add('psmallmatrix', env);
     }
   }
    };
    </script>
    <script type="text/javascript" id="MathJax-script" async
   src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
    </script>
  ```

- _layouts 폴더 밑의 default.html 맨밑에 mathjax_support.html을 인클루드한다. 이때 body문 내에서 (위에 지정하는것이아닌) 제일 마지막 줄에 인클루드를 해준다.

  ```html
  <!-- before -->
  </div>
  
      {% include scripts.html %}
  
    </body>
  </html>
  
  <!-- after -->
      </div>
  
      {% include scripts.html %}
      {% include mathjax_support.html %}
    </body>
  </html>
  ```


  
    
  




## Reference
[1] Github로 블로그 만들기 + LaTeX 적용하기 (https://helloworldpark.github.io/jekyll/update/2016/12/18/Github-and-Latex.html)
[2] GitHub에서 수식 입력 하기 (with LaTex) (https://www.whatwant.com/entry/GitHub-LaTex)
[3] Math support in Markdown (https://github.blog/2022-05-19-math-support-in-markdown/)
[4] github blog와 LaTeX (http://www.ktug.org/xe/index.php?mid=KTUG_open_board&document_srl=248288)

[5] github blog와 latex (https://eeeuns.github.io/2020/12/10/githubblog/)

[6] 007. JeKyll 환경 - (3) 환경설정 기본값 (https://namhoon.kim/2017/03/18/jekyll/007/index.html)

[7] Jekyll,Github 블로그에 LaTex, MathJax 적용, 오류해결 (https://khw11044.github.io/blog/blog-etc/2020-12-21-jekyll-Latex/)

[8] Jekyll Github 블로그에 MathJax로 수학식 표시하기 (https://mkkim85.github.io/blog-apply-mathjax-to-jekyll-and-github-pages/)

[9] github.io 수식 오류 해결하기! (https://an-seunghwan.github.io/github.io/mathjax-error/)
