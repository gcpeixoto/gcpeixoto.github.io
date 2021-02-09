---
title: G-γ - VIM
---

- Install Vim plugins through managers
	- [Pathogen](https://github.com/tpope/vim-pathogen)
	- [Vundle](https://github.com/VundleVim/Vundle.vim) 
	- [vim-plug](https://github.com/junegunn/vim-plug) (using)
	- See a good start at the end of this [post](https://medium.com/@huntie/10-essential-vim-plugins-for-2018-39957190b7a9).

- Easy way to have a `.vimrc` ready to go
	- [Vim-bootstrap](https://vim-bootstrap.com) (very good!)

- How to make uncomment/comment block
	- To uncomment
		1. put cursor on the first `#` character (or other comment operator)
		2. `Ctrl + V`
		3. go down until the last commented line
		4. x` to delete all the `#` vertically
	- To comment
		1. go to the first line you want to comment
		2. `Ctrl + V` to enter in VISUAL BLOCK mode.
		3. select until the last line
		4. press `Shift + I` to put the editor in INSERT mode
		5. press `#` to add a hash to the first line.
		6. press `Esc` twice to insert a `#` on all other selected lines.

- Experience on boosting Vim capabilities
	- See this [post](https://nvie.com/posts/how-i-boosted-my-vim/).

<!--{% highlight bash %} 

{% endhighlight %}--> 

