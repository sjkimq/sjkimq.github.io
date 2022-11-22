---
layout: post
title: git blog latex 적용
categories: git-blog
tag: [latex, blog]
---



## git hub blog latex [9], [5]

- _config.yml 파일의 markdown engine 변경 [9], [5]

  - markdown engine을 kramdown으로 세팅할 것. kramdown의 math blocks가 $$처리를 알아서 해준다. [6]

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
  
- _includes/mathjax_support.html 파일 추가하기

  - `_includes` 폴더에 아래와 같은 내용이 적힌 `mathjax_support.html` 파일을 추가한다 [5]

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

  - `_includes` 폴더에 아래와 같은 내용이 적힌 `mathjax_support.html` 파일을 추가한다 [9]

    ```html
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        TeX: {
          equationNumbers: {
            autoNumber: "AMS"
          }
        },
        tex2jax: {
        inlineMath: [ ['$', '$'] ],
        displayMath: [ ['$$', '$$'] ],
        processEscapes: true,
      }
    });
    MathJax.Hub.Register.MessageHook("Math Processing Error",function (message) {
    	  alert("Math Processing Error: "+message[1]);
    	});
    MathJax.Hub.Register.MessageHook("TeX Jax - parse error",function (message) {
    	  alert("Math Processing Error: "+message[1]);
    	});
    </script>
    <script type="text/javascript" async
      src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
    </script>
    ```

    

- _layouts/default.html 파일 수정

  - 맨밑에 mathjax_support.html을 인클루드한다. 이때 body문 내에서 (위에 지정하는것이아닌) 제일 마지막 줄에 인클루드를 해준다 [5]

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

  - _layouts/defaut.html 파일을 확인했을 때, `<head>`와 `</head>` 사이에 아래와 같은 `use_math`와 `mathjax_support.html`에 관한 명령문이 적혀있어야 한다 [9]

    ```html
    ---
    ---
    
    <!doctype html>
    <!--
      Minimal Mistakes Jekyll Theme 4.17.2 by Michael Rose
      Copyright 2013-2019 Michael Rose - mademistakes.com | @mmistakes
      Free for personal and commercial use under the MIT license
      https://github.com/mmistakes/minimal-mistakes/blob/master/LICENSE
    -->
    <html lang="{{ site.locale | slice: 0,2 | default: "en" }}" class="no-js">
      <head>
        {% include head.html %}
        {% include head/custom.html %}
        {% if page.use_math %}
          {% include mathjax_support.html %}
        {% endif %}
      </head>
    
    (생략)
    
    </html>
    ```
    
    
  
- _includes/scripts.html 파일 수정하기 [9]

  - `_includes` 폴더의 `scripts.html` 파일의 맨 아래에 아래 코드를 추가 [9]

    ```html
    <script type="text/javascript" async
    	src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-MML-AM_CHTML">
    </script>
    
    <script type="text/x-mathjax-config">
       MathJax.Hub.Config({
         extensions: ["tex2jax.js"],
         jax: ["input/TeX", "output/HTML-CSS"],
         tex2jax: {
           inlineMath: [ ['$','$'], ["\\(","\\)"] ],
           displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
           processEscapes: true
         },
         "HTML-CSS": { availableFonts: ["TeX"] }
       });
    </script>
    ```
  
  
  - 아래 링크 참고해서 코드 수정하니 동작 안함
    
    ```html
    <script id="MathJax-script" async
            src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
    </script>
    
    <script type="text/x-mathjax-config">
       MathJax.Hub.Config({
         extensions: ["tex2jax.js"],
         jax: ["input/TeX", "output/HTML-CSS"],
         tex2jax: {
           inlineMath: [ ['$','$'], ["\\(","\\)"] ],
           displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
           processEscapes: true
         },
         "HTML-CSS": { availableFonts: ["TeX"] }
       });
    </script>
    ```
    
    - change a `script` tag that loads MathJax from the CDN (https://github.com/mathjax/MathJax-src)
  






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
