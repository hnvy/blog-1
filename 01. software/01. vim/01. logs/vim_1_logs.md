# Current experience
As I have previously [stated](https://github.com/hnvy/blog-1#about-me), I am not an experienced programmer (though I hope to be one someday. Just think of all of the unlimited doors which you could open!). I used Notepad++ as my primary text editor while writing programs. I still use it (almost every day), but not for programming.

# Why am I (re-)learning Vim now?
Well, when I used Linux, there were a couple of text editors that came pre-installed, and Vim was one of them. So, I launched it, and I couldn't exit the editor. Therefore, I decided to never touch it again, and hence I've forgotten about it.

The other day, I came across a couple of messages online which included pictures of a text editor which had `~` at the start of each line. I instantly remembered where I've seen this before! I also remembered that I still had to tie up some loose ends. So, here I am now.

# What about the beautiful Emacs?
It is definitely on my want-to-do list. The only issue is that Emacs is faster on Linux when compared to Windows (I think it's because of the way the editor is built? I read somewhere that it has something to do with the fact that it loads many small files, which can make Windows a little upset). So, in order for me to get the full sweet Emacs experience, I'd have to go back to Linux (very inconvenient due the reasons outlined [here](https://github.com/hnvy/blog-1#about-me). However, I have had the pleasure to talk with an eminent Emacs user known as Xah Lee. Xah uses Emacs on Windows and has not noticed any issues with regards to performance.

Org-mode is one feature of Emacs that has piqued my interest. I have no idea how it works or why I will need it, but it has piqued my interest. Which brings us to the second issue: lack of time. I have very little time in order to learn how to use Org-mode. The journey is long, and there isn't enough free time at the moment.

Now that we're done with the introduction. Let's get learning! As this file may become very long, here is a link for those who want to read about my [first impression](#e1-19042021---day-0) of Vim.

# E#6 (05/03/2022) - Vim, what does X mean?
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e6-05032022---vim-what-does-x-mean)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e6-05032022---vim-what-does-x-mean)

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

This was originally something I found online, but for some reason the web answer did not work. So I tweaked the code a bit and it worked. In any case, here's the link: https://vim.fandom.com/wiki/Search_the_web_for_text_selected_in_Vim.

# E#5 (21/05/2021) - jump like a rabbit!
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e5-21052021---jump-like-a-rabbit)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e5-21052021---jump-like-a-rabbit)

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
        * You can paste from the system clipboard (rather than from the Vim register) by typing `"+p` or `"+P` (depending on where you prefer to paste the line. You can refer to this [pearl entry](../02.%20pearls/vim_1_pearls.md#e4-10052021---a-clipboard-dilemma) to learn more about the types of pasting in Vim).
    * `Sources`:
        * I used the answer by the user "Martin Tournoij" on [here](https://vi.stackexchange.com/questions/84/how-can-i-copy-text-to-the-system-clipboard-from-vim).

# E#4 (10/05/2021) - a clipboard dilemma.
Updated: (20/05/2021).
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e4-10052021---a-clipboard-dilemma)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e4-10052021---a-clipboard-dilemma)

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
Updated: (19/05/2021).
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e3-21042021---notepad--vim)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e3-21042021---notepad--vim)

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
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e2-20042021---vimtutor)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e2-20042021---vimtutor)

* `GTs`:
    * I found the `vimtutor` file! It took about a minute or two to achieve this.
    * The interface is minimalistic and is not crowded with buttons. I like this quite a lot.
* Time spent: 30
* `LPs`:
    * I found out how to modify the font-size! So, basically I had to write the following `:set: guifont=*`, and this brought up the standard font window that you see in pretty much every text editor. Neat!
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
[Link to pearl entry](../02.%20pearls/vim_1_pearls.md#e1-19042021---day-0)
[Link to pearl entry (HTML)](../02.%20pearls/vim_1_pearls.html#e1-19042021---day-0)

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
