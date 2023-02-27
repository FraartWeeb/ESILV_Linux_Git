# EXERCICE 1

1. Go to the root directory
```
cd /
```
2. Display the content of the current (root) directory
```
ls
```
3. Check your current location
```
pwd
```
4. Try to create a directory named test
```
mkdir test
```
5. Go to the general home directory (should contain folders named after
each user)
```
cd ..
```
6. Go to your home directory
```
cd 
```
7. Go back to the general home directory (located "just above")
```
cd ..
```
8. Go again "just above", you should be back to the root directory
```
cd ..
```
9. Go directly to your home directory (named after you). It should be a
very simple command, which take no name as parameter of the path
```
cd 
```
10. Try to create a directory named test
```
mkdir test
```
11. Go into this new directory
```
cd test
```
12. Check your current location
```
pwd
```

# EXERCICE 2

1. Go to your home directory (should be named after you, you might be
there by default)
```
cd
```
2. Check your current location
```
pwd
```
4. Create a folder linux_ex_1
```
mkdir linux_ex_1
```
5. Go into this folder
```
cd linux_ex_1
```
6. Create an empty text file named [first_name]_[last_name].txt (e.g. alexis_bogroff.txt)
```
touch arthur_frachon.txt
```
7. Create a folder notes
```
mkdir notes
```
8. Move your text file into this folder
```
mv arthur_frachon.txt notes 
```
9. Rename the text file by appending the current year [first_name]_[last_name]_[current_year].txt
```
mv arthur_frachon.txt arthur_frachon_2023.txt
```
10. Make a copy of this folder, name it notes_2022
```
cd ..
cp -R notes notes_2023
```
11. Delete the first folder (notes) using the verbose option
```
rm -r notes
```


# Exercice 3

1. Create a script script_1.sh in the folder linux_ex_1
```
nano script_1.sh
```
2. In the script, write the commands that would output the following :
Script running please wait ...
Done.
```
echo "Script running please wait ..."
```
3. Quit editing and save the script
```
Ctrl X, Yes, Enter
```
4. Display the content of the script (using a command, not from an editor)
```
cat script_1.sh
```
5. Run the script
```
chmod +x script_1.sh
./script_1.sh
```


# Exercice 4

## 4.1 Change the rights for accessing or modifying a file

1. Create a file credentials in the folder linux_ex_1
```
touch credentials.txt
```
(a) Write any kind of (fake) personal information within the file
```
vi credentials.txt
Press I, write, Press Echap, :w, enter, :q, enter
```
(b) Display the file content
```
cat credentials.txt
```
(c) Display the current permissions
```
ls -ls
```
2. Change the current permissions to : read only for all users
```
chmod 444 credentials.txt
```
(a) Display the new permissions
```
ls -l
```
(b) Modify and save the file
```
vi credentials.txt
Insert -> Warning : Changing a readonly file
:q! to quit without changes
```
(c) Display the file content
```
cat credentials.txt
```
3. Change the permissions back to read and write for all users
```
chmod 666 credentials.txt
```
(a) Display the new permissions
```
ls -l
```
(b) Modify and save the file
```
vi credentials.txt
Insert : Works well
```
(c) Display the file content
```
cat credentials.txt
```

On the same file :
1. Add the execute permission to the owner
```
chmod 766 credentials.txt
```
(a) Display the new permissions
```
ls -l
```
2. Remove the read permission to other users
```
chmod 722 credentials.txt
```
(a) Display the new permissions
```
ls -l
```
3. Change the permissions to read, write and execute for all users
```
chmod 777 credentials.txt
```
(a) Display the new permissions
```
ls -l
```

## 4.2 Access root files

1. Go to the root folder
```
cd
```
2. Create a file in root user mode named .private_file
```
touch .private_file
ls
-> Does not appear
ls -a 
-> Appears
```
(a) Write some information in the file
```
vi .private_file
```
(b) Display the file content
```
cat .private_file
```
(c) Display all the files in the folder including hidden files
```
ls -a
```
3. Modify the file in normal user mode
```
su - fraart
write password
vi .private_file
```
(a) Write some new information in the file
```
I + text + Esc + :w + :q
```
(b) Display the file content
```
cat .private_file
```
4. Modify the file in root user mode
```
su - root
```
(a) Write some new information in the file
```
vi .private_file
```
(b) Display the file content
```
cat .private_file
```
5. Change permissions to read, write and execute for all users
```
chmod 777 .private_file
```
(a) Modify the file content in normal user mode
```
vi .private_file
```
(b) Display the file content
```
cat .private_file
```

## 4.3 Change a file owner

1. Change permissions of .private_file to read and write for all users, in
normal user mode
```
chmod 666 .private_file
```
2. Set the new file owner as the current user
```
chown $(whoami) .private_file
```
3. Change permissions of .private_file to read and write for all users, in
normal user mode
```
chmod 666 .private_file
```

## 4.4 Manage Packages (tools / functions)

1. Update your main package manager named apt
```
sudo apt update
```
2. Upgrade apt
```
sudo apt upgrade
```
3. Install the package cmatrix
```
sudo apt install cmatrix
```
4. Launch cmatrix
```
cmatrix
```
5. Quit cmatrix
```
Ctrl + C
```
6. Install the package tmux
```
sudo apt install tmux
```
7. Launch tmux
```
tmux
```
8. Say "Hello session 0" using bash in your current tmux session
```
echo "Hello session 0"
```
9. Launch cmatrix in your current tmux session
```
cmatrix
```
10. Detach from the current tmux session (without stopping cmatrix)
```
Ctrl + b ; d
```
11. Create a new tmux session
```
tmux new
```
12. Say "Hello session 1" using bash in your new tmux session
```
echo "Hello session 1"
```
13. Detach from the current tmux session
```
Ctrl + d
```
14. List all running sessions
```
tmux ls
```
15. Attach again to session 0
```
tmux a -t 0
```
16. Detach again
```
Ctrl + b ; d
```
17. Attach again to session 1
```
tmux a -t 1
```
18. Detach again
```
Ctrl + b ; d
```
19. List all running sessions
```
tmux ls
```
20. Kill all tmux sessions and quit tmux
```
tmux kill-server
```
21. List all sessions
```
tmux ls
```

## Exercice 4.5 Use functions arguments / parameters

1. Display the cmatrix help function
```
cmatrix -help
```
2. Launch cmatrix and make it display white characters (in place of the
green)
```
cmatrix -C white
```
3. Re-launch cmatrix and slow down the speed of characters actualization
```
cmatrix -u 8 (default = 4)
```
4. Stop cmatrix
```
Ctrl + c
```
5. Launch cmatrix with both :
```
cmatrix -C white -u 8
cmatrix -r
```
