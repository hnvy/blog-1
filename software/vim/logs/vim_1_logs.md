# Current experience
As I have stated [previously](https://github.com/hnvy/blog-1#about-me), I am not an experienced programmer (though I hope to be one someday. Just think of all of the unlimited doors which you could open!). I used Notepad++ as my primary text editor while writing programs. I still use it (almost every day), but not for programming.

# Why am I (re-)learning Vim now?
Well, when I used Linux, there were a couple of text editors that came pre-installed, and Vim was one of them. So, I launched it, and I couldn't exit the editor. Therefore, I decided to never touch it again, and hence I've forgotten about it.

The other day, I came across a couple of messages online which included pictures of a text editor which had `~` at the start of each line. I instantly remembered where I've seen this before! I also remembered that I still had to tie up some loose ends. So, here I am now.

# What about the beautiful Emacs?
It is definitely on my want-to-do list. The only issue is that Emacs is faster on Linux when compared to Windows (I think it's because of the way the editor is built? I read somewhere that it has something to do with the fact that it loads many small files, which can make Windows a little upset). So, in order for me to get the full sweet Emacs experience, I'd have to go back to Linux (very inconvenient due the reasons outlined [here](https://github.com/hnvy/blog-1#about-me). However, I have had the pleasure to talk with an eminent Emacs user known as Xah Lee. Xah uses Emacs on Windows and has not noticed any issues with regards to performance.

Org-mode is one feature of Emacs that has piqued my interest. I have no idea how it works or why I will need it, but it has piqued my interest. Which brings us to the second issue: lack of time. I have very little time in order to learn how to use Org-mode. The journey is long, and there isn't enough free time at the moment.

Now that we're done with the introduction. Let's get learning! As this file may become very long, here is a link for those who want to read about my [first impression](#e1-19042021---day-0) of Vim.

# E#2 (20/04/2021) - vimtutor.
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