The 11 Steps to Learning Vim
============================

*"I used to like coding. It’s fun to see numbers and letters turn into something so much more. But now, thanks to Vim, I love coding. Have you ever dreamt you could fly? There’s nothing like it, but you can have a taste of it when you code with Vim."*

- Franky Chung, [How Did I Ever Get Along Without](http://franky.co/2011/03/how-did-i-ever-get-along-without)

Step 1
------

Step 1 is me asking you to take a leap of faith when I say: Ignore everything that has been said about VIM's difficulty.  It's not so bad, really.  The learning process is like a game where the controls need to be felt by touch, and the very first -- and only, in my opinion -- learning curve is figuring out how to get your cursor from line A to line B or C, comfortably, using your home row keys (`h`, `j`, `k` and `l`).  Once this strangeness has been overcome, things start to click. This is very human and natural; like being able to walk, movement is freedom.  When people first boot Vim all of the techniques that they've learned to navigate over the years are no longer available.  This is the key:  `h`, `j`, `k` and `l`, four commands:  `h` for left, `j` for down, `k` for up and `l` for right.  Keep this in the back of your mind as you read on.


Step 2
------

Step 2 is to think about your text editor for a second. Like really think about it, and how much you use it. If you're a Sublime Text user, remember when it first hit the scene? Much of the joy came from users of TextMate, who felt as though their beloved environment had been abandoned. Sublime Text filled that gap by introducing a system for importing TextMate plugins as well as extending common functionality. But it was a hassle, and now Sublime Text, too, seems to have followed in the wake of TextMate with stale releases and a fairly unresponsive development team. You use your editor every day, generally for eight hours or more. Editors come and go. Vim, on the other hand, has persistence. It is guaranteed to be on all Linux-based systems, and as such will continue to have developers adding and extending its core. Vim will be the last text editor you will ever have to learn, and will ever need. By taking steps to learn it you are making a substantial time investment in your future.


Step 3
------

Step 3 is recognizing that learning Vim is much more than just not having to learn other systems or adapt to change. Vim is a way of thinking about editing text that is much more precise and more focused than other systems. The subtitle of the book Practical Vim says it all: "Edit Text at the Speed of Thought." Thought—how does visual perception work? You sense something in the periphery that you want to focus on and your eyes move toward it. Vim is the same way, but with the added benefit of being able to act. (Unfortunately you can't `move bird two trees over, three branches up`!) It allows the user a pinpoint precision that mirrors the way we already perceive things in the physical world but with an immediate ability to manipulate the subject at hand. As you get more proficient you find there are no more intermediary steps; you think and the change occurs, literally.

Step 4
------

Step 4 is about learning from others, and particularly the doubters. Read this post by Yehuda Katz, who tried, failed, and then realized he was simply looking at it from the wrong angle, [Everyone Who Tried to Convince Me to use Vim was Wrong](http://yehudakatz.com/2010/07/29/everyone-who-tried-to-convince-me-to-use-vim-was-wrong/), as well as this post from Jon Beltran de Heredia, which fills in the details and provides a few concrete examples: [Why, oh WHY, do those #?@! nutheads use vi?](http://www.viemu.com/a-why-vi-vim.html)

Step 5
------

Step 5 is to begin your quest. **THIS IS IMPORTANT!** Open up your terminal and type in `vimtutor`. All of the basics are covered here, particularly navigation —h, j, k and l. It will feel weird, but complete it. And then after, open up a text document and practice navigating around changing words. Like I said in Step 1, being able to navigate in the most basic of ways serves to break the fear. It will empower you to continue learning. You cannot learn to run without knowing how to walk. Those four commands are the most important.

Step 6
------

In Step 6, you will cast off on your own. Vim, as it comes out of the box, is notoriously bare. Lots of the cannot-live-without functional things like copy/paste, tabs, syntax highlighting, etc., are turned off by default. This is due to the need for maximum interoperability with existing environments as well as extensibility — Vim is designed to give the user what he or she wants. It does not mean that the options are not there, though unfortunately this can be unclear.

Knowing this, what I did was begin to search for simplistic, initial `.vimrc` configurations to get me started.  For those who do not know, `.vimrc` is the configuration file used to define your editing environment.  Everything you need to do should generally be configured here.  Stumbling upon this reddit thread -- [Looking for a good, well-commented .vimrc with sane defaults to get me started](http://www.reddit.com/r/vim/comments/1jleqc/looking_for_a_good_wellcommented_vimrc_with_sane/) -- I found a comment that served as a totally perfect starting point:

```
filetype plugin indent on          " filetype detection and settings
syntax on                          " syntax highlighting
silent! runtime macros/matchit.vim " matchit comes with Vim
set nocompatible                   " not strictly necessary but useful in some scenarii
set backspace=indent,eol,start     " let the backspace key work "normally"
set hidden                         " hide unsaved buffers
set incsearch                      " incremental search rules
set laststatus=2                   " not strictly necessary but good for consistency
set ruler                          " shows line number in the status line
set switchbuf=useopen,usetab       " better behavior for the quickfix window and :sb
set tags=./tags;/,tags;/           " search tags files efficiently
set wildmenu                       " better command line completion, shows a list of matches
nnoremap gb :buffers<CR>:sb<Space> " quick buffer navigation
```

While providing the above example as a good bare minimum, s/he notes, *"Taking someone else's vimrc whole sale is the second worst thing you could do as a beginner. The worst thing would be to use a distribution like janus or spf13: stay away!"*

Heed this warning and build your configuration file from scratch.  Initially, in my excitement, I tried to jump a few steps and found Square's post about their Vim distribution ([Fly Vim First Class](http://corner.squareup.com/2013/08/fly-vim-first-class.html)) and after installing it had absolutely no clue -- like no clue whatsoever -- how to use it.  Oops!  Back to Sublime Text.  Don't do this.

Use the above for your first configuration.  This will give you sane, typical text editor defaults.  At the very least, you should now be able to code.

Step 7
------

Next, you need to ask yourself what the most important features of your current text editor are. Do you like the fuzzy finder in Sublime Text? Or the package manager that allows you to seamlessly extend the core functionality of your editor? Do you like the ability to navigate between tabs and "ctrl-click" to different Class definitions? Autocomplete? If so, you’re in luck: Vim's community is absolutely MASSIVE, and the key to this awesome massiveness is [Vundle](https://github.com/gmarik/Vundle.vim), a Package Control-like environment for installing plugins, otherwise known as Bundles. From here I was able to very quickly build up the resources I needed to code efficiently, while simultaneously learning the Vim environment and ecosystem. Integrating Vundle was a breeze; I simply cloned the repo and edited my `.vimrc` file so that it could hook into the library. From there, I was only a few Google searches away from finding what I needed, namely:

- [NERDTree](https://github.com/scrooloose/nerdtree), which provides a docked sidebar for navigating your filesystem
- [GitGutter](https://github.com/airblade/vim-gitgutter) for seeing which lines have changed during editing
- [ColorSchemes](https://github.com/flazz/vim-colorschemes) for making my editing environment look good
- [CtrlP](https://github.com/kien/ctrlp.vim) for fuzzy-finding files within my project directory
- [Syntastic](https://github.com/scrooloose/syntastic) for doing runtime error and syntax checking
- [YouCompleteMe](https://github.com/Valloric/YouCompleteMe) for autocomplete; and
- [Airline](https://github.com/bling/vim-airline) for completing my editing environment with tabs (which are really buffers) as well as color highlighting of different modes via status-bars.  This, in my opinion, is the single most important addition to my Vim setup as it *really* allowed me to see what was going on and I would recommend everyone install it immediately.

Step 8
------

Step 8 is more setup, again via the community. **LOOK AROUND!** Many of the settings that I've found to be essential came directly from looking at other people’s vimfiles, usually located within their `dotfile` repos on GitHub. [Justin Reidy](https://github.com/jmreidy/dotfiles) and [Aaron Jenson](https://github.com/aaronjensen/vimfiles) both have particularly good collections of snippets. Once you get going you'll start to find there are things you would like to be able to do but just don't know how to. The community has solved this, and generally `.vimrc` files are well documented so that others can share.

Step 9
-------

Step 9 is merely a reminder: Whatever you are doing could be done better. From deleting code from in between brackets to navigating from line 10 to 43 and deleting the third word, there's a command for that. Commands like... `dap` —meaning, "delete a paragraph". Or `ci"`, "change and insert between quotes." See how they flow? Everything has a sort of mnemonic quality to it that assists in memorizing. And these commands can be combined, spelling sentences of operation. Genius. So remember, whatever it is you are doing could be done better, and if what you want to do can't be accomplished in two or three commands, google it. It exists.

Step 10
-------

By Step 9 you should be editing code and feeling more comfortable. This is when the note taking should begin. Mac OSX ships with Notes, a simple app for jotting down your thoughts, but there are any number of apps that can accomplish similar tasks. What I did was begin recording Vim commands that I knew I should know, or will soon need to know, and at the beginning of each workday I would revisit and practice what I learned the day before. It's incredible how much you can learn simply by taking a note, trying it a few times, sleeping on it, and then revisiting it in the morning. This becomes your "cheat sheet." Once I got into this habit, I learned all the essential key commands pretty much immediately. I can't emphasize how important it is to do this! Do it, and keep it open in your second monitor.

Step 11
-------

Step 11 is the final step, when you abandon your default terminal Vim and download MacVim, which is faster, a stand alone app, and will complete the cycle: `brew install macvim --override-system-vim`. From the command line, launch it via `mvim` instead of `vim`. This will bring some of the niceties of more conventional editors back into your environment like speed, stability, draggable window panes, the scroll wheel, and so on.

(And one last parting thought)
------------------------------

Try to learn a new language or framework while also learning Vim. When I started at my most recent job I was tasked with learning Rails. From previous quick-learning experience that didn't seem to stick, I realized that if I didn't really know my editor — and really, couldn't even type — I also couldn't touch-type text off of tutorials or out of books. It forced me to really look and try to understand what I was doing, since the doing was no longer being accomplished by automatic-memory. And so far, the experiment has been remarkably productive in ways I couldn't even imagine. I feel like this is **the** way to learn a new language. Too bad it can only happen once :/

---

That's it. Go forth! And for those who are curious, my `.vimrc` file is [located here](https://github.com/damassi/dotfiles/blob/master/.vimrc) and should provide a good amount of direction for some of the common tasks normally expected out of the box from editors like Sublime Text.

Hope this provides some clarity, and remember: Regardless of the initial confusion and difficulty in getting started, you're making your future developer self immensely more productive by diving in and taking the plunge. Seriously. I'm just a few weeks in right now and I can positively say that learning Vim has been the best work-related decision of my life. It's fun, and in the strangest of ways it makes you think better.

If you have any questions, comments, edits or advice feel free to open a PR :)
