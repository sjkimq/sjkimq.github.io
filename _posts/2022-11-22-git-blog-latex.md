---
layout: post
title: git blog latex 적용
categories: git-blog
tag: [latex, blog]
---



## git hub blog latex [5]

- _includes 폴더 밑에 Mathjax.html 파일을 만들고 다음 내용을 넣는다.

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

- _layouts 폴더 밑의 default.html 맨밑에 Mathjax.html을 인클루드한다. 이때 body문 내에서 (위에 지정하는것이아닌) 제일 마지막 줄에 인클루드를 해준다.

  ```html
  <!-- before -->
  </div>
  
      {% include scripts.html %}
  
    </body>
  </html>
  
  <!-- after -->
      </div>
  
      {% include scripts.html %}
      {% include Mathjax.html %}
    </body>
  </html>
  ```

- 마크다운을 kramdown로 세팅할 것. kramdown의 math blocks가 $$처리를 알아서 해준다.



## Reference
[1] Github로 블로그 만들기 + LaTeX 적용하기 (https://helloworldpark.github.io/jekyll/update/2016/12/18/Github-and-Latex.html)
[2] GitHub에서 수식 입력 하기 (with LaTex) (https://www.whatwant.com/entry/GitHub-LaTex)
[3] Math support in Markdown (https://github.blog/2022-05-19-math-support-in-markdown/)
[4] github blog와 LaTeX (http://www.ktug.org/xe/index.php?mid=KTUG_open_board&document_srl=248288)

[5] github blog와 latex (https://eeeuns.github.io/2020/12/10/githubblog/)
