Pipes and counting lines: 

Pipe sends the output : ls /etc | wc -l           # how many entries live in /etc 
ls -a ~ | grep '^\.'                              # only entries starting with a dot (dotfiles) 


/root/home-contents.txt - the full listing of /home (one entry per line). If /home is empty on this machine, list /root instead so the file is non-empty. 
if [ -n "$(ls /home)" ]; then ls /home > /root/home-contents.txt; else ls -a /root > /root/home-contents.txt; fi 

 
/root/home-count.txt - a single number: how many entries are in /home. 
ls /home | wc -l > /root/home-count.txt 


/root/bin-count.txt - a single number: how many entries are in /bin. 
ls /bin | wc -l > /root/bin-count.txt 

head and tail: peek at either end 

head/tail = 10 lines default, -n N to change

head /etc/os-release 

head -n 3 /etc/os-release      # first 3 lines only 

tail -n 5 /etc/passwd          # last 5 lines 

wc: count lines, words, bytes 

wc -l /etc/passwd 

Piped from another command, wc -l becomes "how many things did that produce": 

ls /etc | wc -l           # how many entries live in /etc 
