---
type: rule
archivedreason: 
title: Do you use Web Compiler extension?
guid: bf5b98f8-6720-41da-9ee3-48ecf6d1e534
uri: do-you-use-web-compiler-extension
created: 2018-06-19T01:38:21.0000000Z
authors:
- id: 76
  title: Eden Liang
related: []

---

You can use Visual Studio's Web Compiler extension to create a bundle.css and test if CSS was compiled successfully. 

<!--endintro-->

More information and download at [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.WebCompiler).
<dl class="goodImage">&lt;dt&gt; <img src="web-compiler-find-error.png" alt="web-compiler-find-error.png"> &lt;/dt&gt;<dd>Figure: Web Compiler can find missing curly braces</dd></dl> Unfortunately different kinds of errors, like are not caught. <dl class="badImage">&lt;dt&gt; <img src="web-compiler-didnt-find-error.png" alt="web-compiler-didnt-find-error.png"> &lt;/dt&gt;<dd>Figure: Curly braces in the wrong place, but still compiled successfully <br></dd></dl>
In addition, Gulp is wrongly successful too:
<dl class="badImage">&lt;dt&gt;<img src="gulp-didnt-find-error.png" alt="gulp-didnt-find-error.png"> &lt;/dt&gt;<dd>Figure: Gulp couldn't find the curly braces error<br></dd></dl>