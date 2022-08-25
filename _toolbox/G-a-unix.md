---
title: G-α - Unix & alike
---

## Terminal Useful Commands

{% highlight liquid %} 
{% raw %}
# ==== MISC

diff -w [file1] [file2] > [diffFile]

open -a [application] [file]

echo -e "first_line \n second_line" (with -e); 

ssh -v [username]@[firewall] -t ssh [username]@[internal] 

sshfs [username]@hostname:[path_to_remote_dir]  [path_to_local_dir]

screen -S [name_of_background_screen]; 

control-a-d (escape screen mode); 

control-a-[ (enable scrollback mode)

curl "[url_address]" (linux's wget dude)

echo "hello, world!" | tee path_to_file ('tee' command to pipe standard output to somewhere)

iconv -f original_encoding -t new_encoding original_file > new_file (change charset)

file -I <filename> (know encoding)

nmap -n -sP 10.0.0.0/24 (ping for several hosts)

top -d [number_of_seconds] (check processes passing delay)

awk '{print FNR "\t" $0}' path_to_file.txt | open -f (add pseudo linenumbers into TextEdit; use opt+drag for text selection) 
​​{% endraw %}
​{% endhighlight %}
​
​{% highlight liquid %} 
{% raw %}
# ==== HOTKEYS


^+A: go to beginning of line
^+E: go to end of line
^+U: clean up entire line
^+y: recall the deleted command
^+K: delete forward cursor position
^+W: delete backward cursor position
^+C: cancel command
^+L: clear entire prompt
^+R: search on history; type again to run through history 
{% endraw %}
​{% endhighlight %}


{% highlight liquid %} 
{% raw %}
# ==== Sun Grid Engine essentials
qsub

qdel pid; -u username

qstat -f; -explain; -j; -j jobid; -F [attributes] 

qhost -j
{% endraw %}
​{% endhighlight %}
​
## macOS keyboard fast symbols

{% highlight liquid %} 
{% raw %}
Fast symbols with option button + keys on Mac:
opt + 1,2,3,4,5,6,7,8,9,0 --> ¡,™,£,¢,∞,§,¶,≤,•,ª,º
opt + q,w,e,r,t,y,u,i,o,p --> œ,∑,´,®,≤,†,¥,¨,ˆ,ø,π
opt + a,s,d,f,g,h,j,k,l --> å,ß,∂,≤,ƒ,≤,©,≤,˙,∆,˚,¬
opt + z,x,c,v,b,n,m --> Ω,≈,ç,√,∫,˜,µ
opt + = --> ≠
opt + [, ], \ --> “,‘,«
opt + ;, ' --> …,Æ
opt + , ,. ,/ --> ≤,≥,÷- 

opt + shift + [key] --> several
opt + shift + k --> 
opt + shift + 2 --> €
opt + shift + 8 --> °
opt + shift + v --> ◊
{% endraw %}
​{% endhighlight %}
​
## Misc
​
- How to record voice over: using command `say` to read file and output as audio:

{% highlight shell %} 
say -f file.txt -o output_file.aiff -r <rate_in_words_per_minute> -v [alex, bruce, luciana, etc]
{% endhighlight %} 

### .zshrc and .zshenv

- macOS is now using [Z Shell](http://zsh.sourceforge.net) as default shell.
- Add preferences to `~/.zshrc;`. Then update with `source ~/.zshrc`.
- If a `.bash_profile` exists, the quick way to get things working as before is to create a `.zshenv` and pull back current settings with `echo source ~/.bash_profile > ~/.zshenv && source ~/.zshenv`; see [here](https://stackoverflow.com/questions/23090390/is-there-anything-in-zsh-like-bash-profile).


### Convert image files in batch mode

- Replaces X,Y by PNG/JPEG/TIF (problem with EPS?)

{% highlight shell %} 
for i in *; do sips -s format X $i --out $i.Y; done
{% endhighlight shell %} 

- [ImageMagick](http://www.imagemagick.org/script/convert.php)

{% highlight shell %} 
brew install imagemagick; magick convert A.jpg A.png
{% endhighlight shell %} 

	
### Create password-protected zip file

{% highlight shell %} 
zip -er file.zip folder_to_zip/
{% endhighlight %} 


### Jekyll installation workaround on Apple M1 chips

Jekyll is a good backend for building static sites. However, in the new Apple's M1 chips, some problems with architecture are [alleged](https://www.moncefbelyamani.com/how-to-install-jekyll-on-a-mac-the-easy-way/?utm_source=jekyll-8784
).

A workaround to have Jekyll working on these machines is:

- Not using macOS's embedded _ruby_, but install it from `homebrew`. Follow these [steps](https://jekyllrb.com/docs/installation/macos/)
- Since this new ruby is keg-only and not symbolically linked, add it to `.zshenv` (the .gem executable is required) to have:
{% highlight shell %} 
export PATH="/opt/homebrew/opt/ruby/bin:$PATH"
export PATH="$HOME/.gem/ruby/3.1.0/bin:$PATH"
{% endhighlight %} 
- Restart the `shell` and check if `ruby -v` points to the ruby version installed from `brew`.
- Install `jekyll`, `bundler` and `webrick` (necessário) localmente:
{% highlight shell %} 
gem install --user-install bundler, jekyll, webrick
{% endhighlight %} 

### Convert .m4a to .mp3
 
- Install `ffmpeg` with `brew install ffmpeg`
- Use `ffmpeg -i in.m4a -codec:a libmp3lame -qscale:a 1 out.mp3`

### Remove printing restrictions on PDF
 
- Install `qpdf` with `brew install qpdf`
- Use `qpdf --decrypt in.pdf out.pdf`


### Command line PDF to TXT conversion

- Install: `brew install xpdf`
- Usage: `pdftotext in.pdf out.txt`