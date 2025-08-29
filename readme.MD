Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ ls -al ~/.ssh
total 27
drwxr-xr-x 1 Dell 197121   0 Aug 28 08:42 .
drwxr-xr-x 1 Dell 197121   0 Aug 27 22:36 ..
-rw-r--r-- 1 Dell 197121 419 Aug 28 08:42 id_ed25519
-rw-r--r-- 1 Dell 197121 104 Aug 28 14:54 id_ed25519.pub
-rw-r--r-- 1 Dell 197121  92 Aug 27 22:31 known_hosts

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ # Start the ssh-agent in the background

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ eval "$(ssh-agent -s)"
Agent pid 585

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ # Add your private key to the ssh-agent

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ ssh-add ~/.ssh/id_ed25519
Identity added: /c/Users/Dell/.ssh/id_ed25519 (rizwanrka826@gmail.com)

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ ssh -T git@github.com
git@github.com: Permission denied (publickey).

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ cat ~/.ssh/id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIG5OQXYx4Pi08U23rsdf0ZeaOfp4uQnHGwVQxi1W+7BD rizwanrka826@gmail.com

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ ssh -T git@github.com
Hi KhanRiyazi! You've successfully authenticated, but GitHub does not provide shell access.

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ git remote -v
origin  git@github.com:KhanRiyazi/Design-Book.git (fetch)
origin  git@github.com:KhanRiyazi/Design-Book.git (push)

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ git remote set-url origin  git@github.com:KhanRiyazi/Design-Book.git

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ git push origin main
Enumerating objects: 12, done.
Counting objects: 100% (12/12), done.
Delta compression using up to 4 threads
Compressing objects: 100% (10/10), done.
Writing objects: 100% (10/10), 6.76 KiB | 461.00 KiB/s, done.
Total 10 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (6/6), completed with 2 local objects.
To github.com:KhanRiyazi/Design-Book.git
   eff3967..e15b246  main -> main

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ git config --get remote.origin.url
git@github.com:KhanRiyazi/Design-Book.git

Dell@DESKTOP-03NGJG4  ~/Desktop/Teach (main)
$ 