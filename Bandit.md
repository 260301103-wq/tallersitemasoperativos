### Bandit over the wire
# nivel 0 
ssh bandit0@bandit.labs.overthewire.org -p 2220  bandit0
# nivel 0-1
ssh bandit1@bandit.labs.overthewire.org -p 2220 cat readme
# nivel 1-2
ssh bandit2@bandit.labs.overthewire.org -p 2220 cat ./-
# nivel 2-3
ssh bandit3@bandit.labs.overthewire.org -p 2220 cat "spaces in this filname" 
# nivel 3-4
ssh bandit4@bandit.labs.overthewire.org -p 2220 ls -la inhere  cat inhere/.hidden
# nivel 4-5
ssh bandit5@bandit.labs.overthewire.org -p 2220 file inhere/*
# nivel 5-6
ssh bandit6@bandit.labs.overthewire.org -p 2220 find inhere -type f -size 1033c ! -executable
# nivel 6-7
ssh bandit7@bandit.labs.overthewire.org -p 2220 find / -user bandit7 -group bandit6 -size 33c 2> /dev /null
# nivel 7-8
ssh bandit8@bandit.labs.overthewire.org -p 2220 grep "millionth" data.txt
# nivel 8-9
ssh bandit9@bandit.labs.overthewire.org -p 2220 sort data.txt | uniq -u
# nivel 9-10
ssh bandit10@bandit.labs.overthewire.org -p 2220 strings data.txt | grep "=="
# nivel 10-11
ssh bandit11@bandit.labs.overthewire.org -p 2220 base64 -d data.txt 
# nivel 11-12
ssh bandit12@bandit.labs.overthewire.org -p 2220 tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt
# nivel 12-13
ssh bandit13@bandit.labs.overthewire.org -p 2220 xxd -r data.txt > file file tar/ gzip /bzip2
# nivel 13-14
ssh -i sshkey.private bandit14@localhost -p 2220 sshkey.private
# nivel 14-15
ssh bandit15@bandit.labs.overthewire.org -p 2220 nc localhost 30000
# nivel 15-16
ssh bandit16@bandit.labs.overthewire.org -p 2220 openssl s_client -connect localhost:30001
# nivel 16-17
ssh bandit17@bandit.labs.overthewire.org -p 2220 nmap -sV -p 31000-32000 localhost openssl s_client -connect localhost:[puerto]
# nivel 17-18
ssh bandit18@bandit.labs.overthewire.org -p 2220 diff passwords.old passwords.new
# nivel 18-19
./bandit20-do cat /etc/ bandit_pass/bandit20
# nivel 19-20
echo | nc -l -p 4444 & ./suconnect 4444 
# nivel 20-21
ls /etc /cron.d/ cat /etc /cron.d /cronjob_bandit22 cat /usr /bin /cronjob_bandit22.sh cat /tmp
# nivel 21-22
cat/ etc/ cron.d/ cornjob_bandit23 cat/ usr/ bin/ cronjob_bandit23.sh cat /tmp/ & (echo i am the user bandit23 | md5sum |cut -d ' ' -f 1)
# nivel 22-23
cat/ etc/ cron.d /cronjob_bandit24 cat/ usr/ bin/ cronjob_bandit24.sh cd $(mktemp -d) chmod 777 chmod 777 pass.sh touch out.txt chmod 666 out.txt cp pass.sh /var /spool /bandit24 /foo /cat out.txt
# nivel 23-24
cd $(mktemp -d) for i in {0000.9999}; do echo "$i"; done > combos.txt head -3 combos.txt wc -l combos.txt 
# nivel 24-25
ls -la scp -p 2220 bandit25@bandit.labs.overthewire.org:bandit26.sshkey cd $HOME dir bandit26.sshkey icacls bandit26.sshkey /inheritance:r /grant:r "$:R" ssh i bandit26.sshkey -p 2220
# nivel 25-26
ssh bandit26@bandit.labs.overthewire.org -p 2220 :set shell=/ bin/ bash :shell
# nivel 26-27
cd $(mktemp -d) git clone ssh://bandit27-git@bandit.labs.overthewire.org:2220/home/bandit27-git/repo repo27 cd repo27 cat README
# nivel 27-28
git clone ssh://bandit28-git@bandit.labs.overthewire.org:2220/home/bandit28-git/repo repo28 cd reppo28 cat README.md git log git show 
# nivel 28-29
git clone ssh://bandit29-git2bandit.labs.overthewire.org:2220/home/bandit29-git/repo repo29b cd repo29b cat README.md git branch -a git checkout dev cat README.md
# nivel 29-30
git clone ssh://bandit30-git@bandit.labs.overthewire.org:2220/home/bandit30-git/repo repo30 cd repo30 cat README.md git branch -a git tag git show secret
# nivel 30-31
git clone ssh:/bandit31-git@bandit.labs.overthewire.org:2220/home/bandit31-git/repo repo31 cd repo31 cat README.md [System.IO.File]:WriteAllText("$PWD\key.txt", "May I come in?`n") git add -f key.txt git commit -m "add key" git push origin master
# nivel 31-32
$0 whoami cat/ etc/ bandit_pass/bandit33
# nivel 32-33
ls cat README.txt
## FIN DEL JUEGO
