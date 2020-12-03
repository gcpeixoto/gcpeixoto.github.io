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