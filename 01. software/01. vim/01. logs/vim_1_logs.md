<link rel="stylesheet" href="/blog-1/css/main.css">

```
> ./blog-1/01. software/01. vim/01. logs/vim_1_logs.md
```
<p style="text-align: right;"><a href="https://hnvy.github.io/blog-1/">Home page</a></p>
<p><a href="https://github.com/hnvy/blog-1/edit/main/01_software/01_vim/01_logs/vim_1_logs.md">Edit</a></p>
<hr>

# Introduction
See <a href="https://hnvy.github.io/html/about.html#vim">this</a>.

# E#7 (08/07/2022) - contents table in plain text.
[Link to pearl entry](../02_pearls/vim_1_pearls.html#e7-08072022---contents-table-in-plain-text)

Here is how to create an interactive table of contents (well, sort of) in a plain text file.

Your text file must first have some kind of structure that outlines headings. Even though it is not necessary, this step will undoubtedly make your life much simpler.

So, let's say we have the following format:

```
# Heading 1
## Subheading 1.1
## Subheading 1.2
## Subheading 1.3
# Heading 2
# Heading 3
## Subheading 3.1
```

... and you wish to rapidly traverse that file using a table of contents of some kind. What you need to have is as follows (there is really just one thing):
* `sha256`: According to Wikipedia, `sha256` is a "cryptographic hash functions." In other words, it is a function which encodes the text you give it. In fact, you don't even need to use `sha256`. You can using any algorithm which encodes your text. You can even make your own! But, why go through all the trouble of creating your own algorithm when you can use Notepad++ or Vim (as they have this as a built-in feature)?

Since this is the Vim logs (`vim_1_logs.md`) file, here is how you would go about it in Vim:
1. Press `:`
2. Type the following: `let @"=sha256('____')` (replace the `____` with whatever text you want. In this case, the text will be our headings).
3. The command above has now made the `"` register in Vim equal to the `sha256` of our text. So, if you press `p`, Vim will paste the content of the `"` register into your text file. So, to encode `Heading 1`, we will have to write the following `let @"=sha256('# Heading 1')`. The content of the `"` register will now be: `bbc42...e1f03` (this is known as the "hash"). We can use this unique identifier to create our table of contents.
4. Place your cursor at the beginning of the line which has `# Heading 1`, and press `P`. This will paste the hash right before `# Heading 1`. So, you should have something like this `bbc42...e1f03# Heading 1` (I know, it looks quite ugly).
5. Now, press `yy` to yank (or copy) the line.
6. Press `gg` to go back to the start of the text file, and create a heading with a name like `# Table of Contents`.
7. Press `p` to paste the line that we have yanked in the previous step. So, you should end up with something like this:
```
# Table of Contents
bbc42...e1f03# Heading 1
```
8. What we have done is, effectively, create some visible 'link' between the Table of Contents heading and the actual heading in the text file. Again, it looks ugly, but at least it works.
9. Repeat the steps above for the rest of your headings, or, you can use the following macro: `nmap <M-0> ^v$hy:let @"=sha256('<C-r>"')<CR>Pyygg` (this maps the steps 1-6 to `Alt-0`. You can then go down and paste the content using `p`. Also, to ensure that the mapping is wiped and that it does not affect you in the future, execute `unmap <M-0>` after you're done).
10. The end result should be something like this (To use the 'navigation feature', you can place your cursor on the hash that is under the Table of Contents, and press `#`. This will take you straight to the desired heading.):

```
# Table of Contents
bbc42...e1f03# Heading 1
37ce0...bfc1c## Subheading 1.1
96620...01a72## Subheading 1.2
a8a5e...93789## Subheading 1.3
1cb48...e0efi# Heading 2
4ee32...6a839# Heading 3
b1e43...9698f## Subheading 3.1




bbc42...e1f03# Heading 1
Here is some text

37ce0...bfc1c## Subheading 1.1
Some more text!

96620...01a72## Subheading 1.2
Blah blah blah blah...

a8a5e...93789## Subheading 1.3
Running out of text ideas :\

1cb48...e0efi# Heading 2
Maybe I should have used a Lorem Ipsum generator or something...

Second paragraph.

4ee32...6a839# Heading 3
Or maybe, I should have used less headings:
- Reminder
- For
- Me

b1e43...9698f## Subheading 3.1
Anyway, I'm glad that this is done now.
```

# E#6 (05/03/2022) - Vim, what does X mean?
Updated: (27/06/2022)

[Link to pearl entry](../02_pearls/vim_1_pearls.html#e6-05032022---vim-what-does-x-mean)

I've been wondering if I can use Vim to look up a highlighted word/sentence that is in the current buffer. Perhaps, a way that is more practical than:
1. Copy the thing which you want to search up on the internet
2. Open the browser
3. Paste it in the search bar of your browser
4. Press `Enter`

And, to my surprise, there was! Here is what you need to add to your `vimrc`:

`vmap <C-3> "zy:let @z = substitute(@z,' ','+','g')<CR>:exec ":silent ! start https://www.google.com/search?q=". @z. ""<CR><CR>`

So, this is how it works:
1. Go into Visual mode by pressing `v`, and highlight the words of interest
2. Press `Ctrl+3` (by modifying the `<C-3>` in the line of code above, you can make this keyboard shortcut to whatever you want)
3. That's it! Isn't that so convenient?!

This was originally something I found online, but for some reason the web answer did not work. So I tweaked the code a bit and it worked. In any case, here's the link to the original answer: https://vim.fandom.com/wiki/Search_the_web_for_text_selected_in_Vim.

# E#5 (21/05/2021) - jump like a rabbit!
[Link to pearl entry](../02_pearls/vim_1_pearls.html#e5-21052021---jump-like-a-rabbit)

* `GTs`:
    * I have already found out that Vim offers different modes. So, to truly understand this concept, I had to completely forget everything I 'knew' about text editors. The main ones I am using at the moment are: Normal, Insert, and Command.
    * Vim keeps breaking long lines to smaller ones (not just visually wrapping, but actually changing the text). Not sure whether or not this is useful just yet.
* Time spent: 45
* `LPs`:
    * I learned about 2 more different ways which you can save and exit the file in Vim.
	 * In Vim, we have two types of 'words'. For example, Vim can read the following statement as an 11-word sentence or a one-word sentence: "Vim-is-a-modal-text-editor". You can find out more about this by going over to the pearl entry!
* `LNs`:
    * I need to find out how to stop Vim from automatically inserting line breaks.
* `AP` {}: I need to find out how to stop Vim from automatically inserting line breaks when the line is too long. This is quite urgent because, at the moment, I'm not a big fan of this feature (in terms of writing these entries). However, I am sure that it will be useful when writing a piece of code.
* `Review`:
    * I reviewed APE#4
    * `New LPs`:
        * You can paste from the system clipboard (rather than from the Vim register) by typing `"+p` or `"+P` (depending on where you prefer to paste the line. You can refer to this [pearl entry](../02_pearls/vim_1_pearls.html#e4-10052021---a-clipboard-dilemma) to learn more about the types of pasting in Vim).
    * `Sources`:
        * I used the answer by the user "Martin Tournoij" on [here](https://vi.stackexchange.com/questions/84/how-can-i-copy-text-to-the-system-clipboard-from-vim).

# E#4 (10/05/2021) - a clipboard dilemma.
Updated: (20/05/2021)

[Link to pearl entry](../02_pearls/vim_1_pearls.html#e4-10052021---a-clipboard-dilemma)

* `GTs`:
    * I noticed that pressing `p` whilst in Normal mode, does not actually paste the content which I copied outside of Vim. In other words, Vim seems to have its own unique clipboard (which, according to the internet, is called a "register"). Awesome!
    * I have finished going through `vimtutor` twice now. The first time was on 23/04/2021 and the second time was on 25/04/2021. The problem is that I keep forgetting some of the commands due to the lack of use.
    * Fun fact: this entry was written using Vim.
* Time spent: 30
* `LPs`:
    * I learned that the Vim register is separate from the Windows clipboard.
* `LNs`:
    * I need to find out how to access the Windows clipboard rather than the Vim register. 
* `AP` {}: I need to find out how to access the system clipboard rather than the Vim register, which is (as usual) relatively easy to achieve thanks to this thing that is called "the internet".
* `Review`:
    * I reviewed APE#3.
    * `New LPs`:
        * To duplicate a line in Vim, you need to first be in Normal mode (done by pressing Escape on your keyboard). Then, type `yy` on the line which you want to duplicate. This will yank (copy) it. Now, press `P` to paste the line above the current line, or press `p` to paste it below the current line. So, in short, just type `yyp`!
    * `Sources`:
        * Here is the [website](https://stackoverflow.com/questions/73319/how-to-duplicate-a-whole-line-in-vim) which was used.

# E#3 (21/04/2021) - Notepad++ > Vim?!
Updated: (19/05/2021)

[Link to pearl entry](../02_pearls/vim_1_pearls.html#e3-21042021---notepad--vim)

* `GTs`:
    * Vim is great, but I started to notice that there were a couple of features that Notepad++ had, which seem to be not as accessible in Vim. For example, duplicating the current line, auto-complete, case conversion, and macros.
* Time spent: 15
* `LPs`:
    * I learned how to delete the character that is directly under the cursor by pressing the letter `x`. I think this is a better alternative to pressing `del` (which is at the top-right corner of my keyboard). Much more comfortable!
* `LNs`:
    * I need to find out how to duplicate the current line in Vim.
* `AP` {x 10/05/2021}: I need to find out how to duplicate the current line in Vim, which is easy to achieve thanks to the internet!
* `Review`:
    * I reviewed APE#2
    * `New LPs`:
        * I learned how to copy and paste in Vim, it is quite quick and convenient too. All I had to do is press the letter `y` for "yank" (which means "copy" in the Vim lingo), and the letter `p` for "paste".
    * `Sources`:
        * Here is the [website](https://linuxize.com/post/how-to-copy-cut-paste-in-vim/) which was used.

# E#2 (20/04/2021) - vimtutor.
[Link to pearl entry](../02_pearls/vim_1_pearls.html#e2-20042021---vimtutor)

* `GTs`:
    * I found the `vimtutor` file! It took about a minute or two to achieve this.
    * The interface is minimalistic and is not crowded with buttons. I like this quite a lot.
* Time spent: 30
* `LPs`:
    * I found out how to modify the font-size! So, basically I had to write the following `:set guifont=*`, and this brought up the standard font window that you see in pretty much every text editor. Neat!
    * I learned to make the font persistent (see the [comment](https://vi.stackexchange.com/questions/3093/how-can-i-change-the-font-size-in-gvim) by the user "pkout"). I had to use Notepad++ to achieve this because: one, I did not know how to copy/paste text in Vim, and two, I don't know how to open text files via Vim.
    * Using `vimtutor`, I learned that the letter `j` moves the text cursor downwards (because it looks like a down arrow!), and the letter `k` moves it up. The letter `l` moves the cursor to the right, and finally, the letter `h` moves the cursor to the left! It was a little strange to use at the start, but I slowly started to love it.
* `LNs`:
    * I need to learn how to open a text file in Vim (from within the editor).
    * I need to learn how to copy/paste text in Vim.
* `AP` {x 21/04/2021}: I need learn how to copy/paste text in Vim. This should be easy to achieve with a quick Google search.
* `Review`:
    * I reviewed APE#1
    * `New LPs`:
        * I found the location of `vimtutor` in `\Vim\vim82\tutor`. It was simply called `tutor`. To find it, I used the following search string in Windows Explorer `~=tut`.
    * `Sources`:
        * Self-discovery.

# E#1 (19/04/2021) - day 0.
[Link to pearl entry](../02_pearls/vim_1_pearls.html#e1-19042021---day-0)

* `GTs`:
    * Straight away, I noticed that the font was too small! I had no clue how to increase the font-size.
    * There was a README file which didn't have much in it. It was some sort of "here is a list of good links to use when you need help". But it did talk about this `vimtutor`. I need to look into it soon.
    * There is some GUI? I thought it was literally just text cursor and a bunch of commands (this was the case in Linux).
    * I can actually exit the editor this time! `:q!`. This will probably get quite tedious over time (or maybe not!).
* Time spent: 10
* `LPs`:
    * I learned that there seems to be different versions of Vim. For example, I can see that there is `gVim`, `gVim Read only`, and `gVim Easy`, etc. Not entirely sure what they are.
* `LNs`:
    * I need to look into `vimtutor`.
* `AP` {x 20/04/2021}: I need look into `vimtutor`, and find the file location. This should be relatively easy to achieve.
