<link rel="stylesheet" href="/blog-1/css/main.css">

```
> ./blog-1/01_software/02_coding/01_logs/coding_1_logs.md
```
<p style="text-align: right;"><a href="https://hnvy.github.io/blog-1/">Home page</a></p>
<p><a href="https://github.com/hnvy/blog-1/edit/main/01_software/02_coding/01_logs/coding_1_logs.md">Edit</a></p>
<hr>

# Introduction
See <a href="https://hnvy.github.io/html/about.html#coding">this</a>.


# E#1 (28/08/2022) - hello, world! (C)
<pre><span class="comment-delimiter">/</span><span class="comment-delimiter">/ </span><span class="comment">TITLE: 01_intro.c
</span>
<span class="comment-delimiter">/</span><span class="comment-delimiter">/ </span><span class="comment">The following is what we call a dummy program. It literally does nothing:
</span><span class="comment-delimiter">// </span><span class="comment">main () {}
</span>

<span class="comment-delimiter">// </span><span class="comment">---------------------------------------
</span><span class="comment-delimiter">// </span><span class="comment">Let</span><span class="comment">'</span><span class="comment">s print the good old &quot;Hello, World!&quot;
</span><span class="comment-delimiter">/*</span><span class="comment">
~include~ is a called a pre-processor directive. This tells the compiler &quot;What</span><span class="comment">'</span><span class="comment">s up old friend, next time you compile this text file, mind including the contents of the stdio.h (aka standard input/output) file? Okay, cool. Bye!&quot;

The ~stdio.h~ is called a header file. It includes stuff (aka definitions) that we can use in our program. One of these definitions is... you guessed it, ~put~.

In fact, I realised that you can view the content of this ~stdio.h~ file.

On Linux, it is located at ~/usr/include/stdio.h~.
</span><span class="comment-delimiter">*/</span>
<span class="preprocessor">#</span><span class="preprocessor">include</span> <span class="string">&lt;</span><span class="string">stdio.h</span><span class="string">&gt;</span>

<span class="type">i</span><span class="type">n</span><span class="type">t</span> <span class="function-name">main</span>() <span class="comment-delimiter">/</span><span class="comment-delimiter">/ </span><span class="comment">This is called the entry point to the C program.
</span>{
	put(<span class="string">&quot;Hello, World!&quot;</span>);
	<span class="keyword">return</span>(0);
}

<span class="comment-delimiter">/</span><span class="comment-delimiter">/ </span><span class="comment">** TEST 1: Test time! Write a program (from memory!) That prints out the following text: &quot;This is my first ever mini C program. It</span><span class="comment">'</span><span class="comment">s not much, but it</span><span class="comment">'</span><span class="comment">s honest work...&quot;
</span>
</pre>
