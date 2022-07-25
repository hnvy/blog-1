<link rel="stylesheet" href="/blog-1/css/main.css">

```
> ./blog-1/01. software/00. misc/01. logs/misc_1_logs.md
```
<p style="text-align: right;"><a href="https://hnvy.github.io/blog-1/">Home page</a></p>
<p><a href="https://github.com/hnvy/blog-1/edit/main/01.%20software/00.%20misc/01.%20logs/misc_1_logs.md">Edit</a></p>
<hr>

# Introduction
See <a href="https://hnvy.github.io/html/about.html#misc">this</a>.

# E#2 (25/07/2022) - CMD, find X in subdirectories.

Let's imagine that you are searching through a number of files for the string "`please find me`". There are 400 text files in 20 directories. You're unsure of which file that string belongs in.

What's the solution? Well, `findstr`!

`findstr` is a command that runs on CMD. Using `findstr` is very simple (you can run `findstr /?` to get the manual). My favourite arguments to run are:
* `/s`: searches the subdirectories
* `/i`: ignores sentence-case
* `/c:`: allows `findstr` to search for a string than has white spaces

Suppose you have the following directory `c:\Stats\Spreadsheets\`. Also, let's assume that the `Spreadsheets` folder has many files and many subfolders, and you're looking for the "`please find me`" string:
* `findstr /s /i /c:"please find me" "c:\Stats\Spreadsheets\*"` - This can be used if you aren't currently located in the directory.
* `findstr /s /i /c:"please find me" *.*` - this can be used if you are located in the directory.

# E#1 (16/07/2022) - RegEx, match lines to end of file.
In a text file, I recently had to replace something. Starting at a certain text (`PieceOfText`), up until the last line of the file. Here is how I went about it:
```
Find: PieceOfText((.|\n)*)
Replace: Blah blah blah
```

So, with the help of `((.|\n)*)`, the following has been highlighted:

<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
<p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
<p><span style="background-color: red;">PieceOfText</span></p>
<p><span style="background-color: red;">Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span></p>
<p><span style="background-color: red;">Here is the end of the text file. Nice!</span></p>
