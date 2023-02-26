# Popular Linux and Terminal Commands

---

1. **whoami** - command that displays loged in username
    ```sh
    ❯ whoami
    username
    ```

---

2. **man** - displays more info about command.
    ```sh
    ❯ man whoami

    NAME
        whoami – display effective user id

    SYNOPSIS
        whoami

    DESCRIPTION
        The whoami utility has been obsoleted by the id(1) utility, and is
        equivalent to “id -un”.  The command “id -p” is suggested for normal
        interactive use.

        The whoami utility displays your effective user ID as a name.

    EXIT STATUS
        The whoami utility exits 0 on success, and >0 if an error occurs.

    SEE ALSO
        id(1)

    macOS 13.2                       June 6, 1993                       macOS 13.2
    ```

---

3. **clear** - clears your terminal screen. Shortcut: **Cntr + L**

---

4. **pwd** - print name of the current directory.
    ```sh
    ❯ pwd
    /Users/username
    ```

---

5. **ls** - list the content of the folder.
    ```sh
    ❯ ls
    Applications    Downloads       Music           PyVirtualEnvs
    Documents       Movies          Public          VirtualBox VMs
    ```

examples:
- with path specified
    ```sh
    ❯ ls PyVirtualEnvs
    diplom_project djangoenv
    ```

- **ls -l** - list files in the long format.
    ```sh
    ❯ ls -l PyVirtualEnvs
    total 0
    drwxr-xr-x   5 username  staff  160 Dec  1  2018 diplom_project
    drwxr-xr-x  15 username  staff  480 Dec  2  2018 djangoenv
    ```

- **ls -a** - displays hidden files.
    ```sh
    ❯ ls -a PyVirtualEnvs
    .              ..             .DS_Store      diplom_project djangoenv
    ```

---

6. **cd** - change directory.
    ```sh
    ❯ pwd
    /Users/username
    ❯ cd PyVirtualEnvs
    ❯ pwd
    /Users/username/PyVirtualEnvs
    ```

- **cd ..** - move one level back.
- **cd ~** - move to home directory.
- **cd /** - move to root directory.

---

7. **mkdir** - create directory.

- **mkdir summer winter** - create multiple directories.
- **mkdir summer/seeds** - create directory inside existing directory.
- **mkdir -p winter/seeds/lettuce** - create nested direcory and all directories on the way.

---

8. **touch** - create an empty file.

- **touch squash.txt**
- **touch red.pdf orange.png yellow.xlsx** - create multiple empty files.

---

9. **rmdir** - deletes empty directories.
    ```sh
    ❯ mkdir deleteme
    ❯ ls
    deleteme       diplom_project djangoenv
    ❯ rmdir deleteme
    ❯ ls
    diplom_project djangoenv
    ```

---

10. **rm** - remove files and directories.
    ```sh
    ❯ ls
    blue.txt red.pdf
    ❯ rm blue.txt red.pdf
    ❯ ls
    ```

- **rm -v \<filename\>** - display what was removed.
    ```sh
    ❯ ls
    blue.txt red.pdf
    ❯ rm -v blue.txt
    blue.txt
    ```

- **rm -r \<path\>** - remove directories and their content.
    ```sh
    ❯ ls test_dir
    red.pdf
    ❯ rm -r test_dir
    ❯ ls test_dir
    ls: test_dir: No such file or directory
    ```

- **rm -ri \<path\>** - remove directories and their content but comfimation is needed.
    ```sh
    ❯ ls test_dir
    cat   dog   snake
    ❯ rm -ri test_dir
    examine files in directory test_dir? y
    remove test_dir/cat? y
    remove test_dir/dog? y
    remove test_dir/snake? y
    remove test_dir? y
    ❯ ls test_dir
    ls: test_dir: No such file or directory
    ```

---

11. **open** - open files and directories. Files are opened in the default applications for file extension. This command is MacOs specific.

Ubuntu alternative is **xdg-open**.

---

12. **mv** - move files and folders. Also can rename files/folders.

- **mv \<initial_file_name\> \<new_file_name\>** - rename file.
    ```sh
    ❯ ls
    jornal.txt
    ❯ mv -v jornal.txt journal.txt
    jornal.txt -> journal.txt
    ❯ ls
    journal.txt
    ```

- **mv \<path_to_file\> \<destination_folder>** - move file.
    ```sh
    ❯ mv -v journal.txt test_mv
    journal.txt -> test_mv/journal.txt
    ```

---

13. **cp** - copy files. Syntax similar to move.

- **cp -r /<path_to_folder/> /<destination_path>** - to copy folder with content.

---

14. **head** - outputs the first part of files. By default print the frist 10 lines of each file to standart output.

- **head -n 5 04_popular_linux_terminal_commands.md**
    ```sh
    ❯ head -n 5 04_popular_linux_terminal_commands.md
    # Popular Linux and Terminal Commands

    ---

    1. **whoami** - command that displays loged in username
    ```

---

15. **tail** - outputs the last part of files. By default print the last 10 lines of each file to standart output.

---

16. **date** - display the current date and time.

    ```sh
    ❯ date
    Wed Feb 22 18:39:04 EET 2023
    ```

- **date > today.txt** - write current date and time to the file.

- **date >> taoday.txt** - write current date and time to the file without overwriting content.

---

17. **cat** - concatenate files and print on the standard output.

- **cat \<path_to_file1\> ... \<path_to_filen\>** - display content of multiple files
    ```sh
    ❯ cat contents dates
    total 0
    drwxr-xr-x  4 username  staff  128 Feb 22 22:39 .
    drwxr-xr-x  6 username  staff  192 Feb 22 18:12 ..
    -rw-r--r--  1 username  staff    0 Feb 22 22:39 contents
    drwxr-xr-x  3 username  staff   96 Feb 22 18:14 test_mv
    Wed Feb 22 22:40:09 EET 2023
    ```

- **cat \<path_to_file1\> ... \<path_to_filen\> > \<new_file\>** - creates new file with concatinated content of files listed before '>'.
    ```sh
    ❯ cat contents dates > combined_content
    ❯ cat combined_content
    total 0
    drwxr-xr-x  4 username  staff  128 Feb 22 22:39 .
    drwxr-xr-x  6 username  staff  192 Feb 22 18:12 ..
    -rw-r--r--  1 username  staff    0 Feb 22 22:39 contents
    drwxr-xr-x  3 username  staff   96 Feb 22 18:14 test_mv
    Wed Feb 22 22:40:09 EET 2023
    ```

- **cat -n \<path_to_file\>** - display line numbers.
    ```sh
    ❯ cat -n contents
        1    total 0
        2    drwxr-xr-x  4 username  staff  128 Feb 22 22:39 .
        3    drwxr-xr-x  6 username  staff  192 Feb 22 18:12 ..
        4    -rw-r--r--  1 username  staff    0 Feb 22 22:39 contents
        5    drwxr-xr-x  3 username  staff   96 Feb 22 18:14 test_mv
    ```

---

18. **less** - command to read files. Allows scroling.

- type **'/'** when file is opened to initiate search

---

19. **echo** - prints to the output the argument passed to it.

- **echo "content" >> \<path_to_file\>** - writes "content" value to the file.

---

20. **wc** - counts words in the input.

- **wc \<path_to_file\>** - counts number of words, number of lines, and number of bites.
    ```sh
    ❯ wc contents
        5      38     254 contents
    ```

- **some command | wc** - counts worlds, lines, and bites in the output of the command.
    ```sg
    ❯ docker images | wc
        2      13     125
    ```

    ```sh
    ❯ cat file1 file2 | wc -l
    number of lines in 2 files
    ```

---

21. **sort** - sort or merge records (lines) of text and binary files.

- **sort \<path_to_file\>** - sorts content of the file.
    ```sh
    ❯ sort nums
    2
    234
    54
    6
    999
    ```

- **sort -n \<path_to_file\>** - numeric sort.

- **sort -nr \<path_to_file\>** - numeric reverse sort.

    ```sh
    ❯ sort -nr nums
    999
    234
    54
    6
    2
    ```

---

22. **uniq** - report or omit repeated lines.

- **sort \<file_name\> | uniq** - display distinct values from file. If call **uniq** on file without sorting it only removes duplicates that goes one by one.
    ```sh
    ❯ sort colors.txt | uniq
    black
    blue
    brown
    orange
    red
    white
    yellow
    ```

- **sort \<file_name\> | uniq -d** - display only duplicates.
    ```sh
    ❯ sort colors.txt | uniq -d
    blue
    orange
    ```

- **sort \<file_name\> | uniq -u** - display lines that dont have duplicates.
    ```sh
    ❯ sort colors.txt | uniq -u
    black
    brown
    red
    white
    yellow
    ```

- **sort \<file_name\> | uniq -c | sort -nr** - display how many times line appers in the file and sort output.
    ```sh
    ❯ sort colors.txt | uniq -c | sort -nr
        5 blue
        3 orange
        1 yellow
        1 white
        1 red
        1 brown
        1 black
    ```

---

23. **diff** - find difference between two files.

- **diff \<file1> \<file2>**
    ```sh
    ❯ diff colors.txt favColors.txt
    14d13
    < grey
    ```

- **diff -y \<file1> \<file2>** - display files content side by side.
    ```sh
    ❯ diff -y colors.txt favColors.txt
        red                                     red
        blue                                    blue
        blue                                    blue
        yellow                                  yellow
        blue                                    blue
        orange                                  orange
        blue                                    blue
        orange                                  orange
        black                                   black
        orange                                  orange
        white                                   white
        brown                                   brown
        blue                                    blue
        grey                                    <
    ```

---

24. **find** can be used to find files or folders matching a particular search pattern. It searches recursively.

- **find \<location> \<search_criteria> \<search_pattern>**
    ```sh
    ❯ find . -name '*.txt'
    ./colors.txt
    ./test_mv/journal.txt
    ./favColors.txt
    ```

- **find . -type d** - search for only directories
    ```❯ find . -type d
    .
    ./test_mv
    ```

- **find . -type f** - search for only files

- **find . -name 'E\*' -or -name 'F\*'** - find anything in our current location that has name started with 'E' or with 'F'.

- **find . -type f -size +100c** - find files that have more than 100 characters (bytes) in them.
    ```sh
    ❯ find . -type f -size +100c
    ./contents
    ./combined_content
    ```

- **find . -type f -size +100c -exec cat {} \;** - execute a command on each result of the search. In this example we run ```cat``` to print the file content. Notice ```\;``` that is terminating command and ```{}``` is filled with the file name at execution time.

---

25. **grep** - can be used to search in files, or be combined with pipes to filter the output of another command.

- **grep -nC 1 \<search_pattern> \<search_file>** - '-n' argument to display line number, 'C 1' argument to display context: 1 line before and 1 line after the line with searched value.
    ```sh
    ❯ grep -nC 1 contents combined_content
    3-drwxr-xr-x  6 serhiiolefirenko  staff  192 Feb 22 18:12 ..
    4:-rw-r--r--  1 serhiiolefirenko  staff    0 Feb 22 22:39 contents
    5-drwxr-xr-x  3 serhiiolefirenko  staff   96 Feb 22 18:14 test_mv
    ```

- **grep -r \<search_patter> \<location>** - search for a match in all files in the location directory and all sub-directories.

---

26. **du** - estimate file space usage.

- **du -h | sort -h | tail -n 5** - display 5 largest folders.
    ```sh
    ❯ du -h | sort -h | tail -n 5
    48M    ./djangoenv/lib
    48M    ./djangoenv/lib/python3.7
    54M    ./diplom_project
    58M    ./djangoenv
    112M   .
    ```

- **du -h | sort -hr | head -n 5** - display 5 largest folders reverse order.
    ```sh
    ❯ du -h | sort -hr | head -n 5
    112M   .
    58M    ./djangoenv
    54M    ./diplom_project
    48M    ./djangoenv/lib/python3.7
    48M    ./djangoenv/lib
    ```

---

27. **df** - is used to get disk usage information.
    ```sh
    ❯ df
    Filesystem     512-blocks      Used Available Capacity iused     ifree %iused  Mounted on
    /dev/disk1s5s1  489620264  17466400 172297368    10%  349475 861486840    0%   /
    devfs                 393       393         0   100%     680         0  100%   /dev
    /dev/disk1s2    489620264   3596112 172297368     3%    2718 861486840    0%   /System/Volumes/Preboot
    /dev/disk1s4    489620264  14682512 172297368     8%       8 861486840    0%   /System/Volumes/VM
    /dev/disk1s6    489620264     13192 172297368     1%      19 861486840    0%   /System/Volumes/Update
    /dev/disk1s1    489620264 279081976 172297368    62% 1501269 861486840    0%   /System/Volumes/Data
    map auto_home           0         0         0   100%       0         0  100%   /System/Volumes/Data/home
    ```

- **df -h .** - display info about filesystem where specified folder is located.
    ```sh
    ❯ df -h .
    Filesystem     Size   Used  Avail Capacity iused     ifree %iused  Mounted on
    /dev/disk1s1  233Gi  133Gi   82Gi    62% 1501277 861479200    0%   /System/Volumes/Data
    ```

---

28. **history** - your shell commands history.

- **history | grep docker | tail -n 2** - displays 2 last docker commands from history.
    ```sh
    ❯ history | grep docker | tail -n 2
    3591  history | grep docker | grep robot
    3593  history | grep docker
    ```

---

29. **ps** - display all running processes. By default displays processes for current user.

- **ps ax** - process for all users.

- **ps axww | grep "Visual Studio"** - find process by its name.

---

30. **top** - show most memory or cpu intensive processes.

---

31. **kill** - used to terminate or signal process by process id.

- **kill -l** to check possible signals.

---

32. **killall** - kill process by name.

---

33. **jobs** - show stopped, suspended jobs

    ```sh
    ❯ jobs
    [1]  + suspended  top
    ```

34. **fg** - resume stopped, suspended job in foreground.

    ```sh
    ❯ fg
    [1]  + 19433 continued  top
    ```

35. **bg** - resume stopped, suspended job in background.

    ```sh
    ❯ bg
    [1]  + 19433 continued  top
    [1]  + 19433 suspended (tty output)  top
    ```

- **&** can be used to run process in the background, example: **sleep 50 &**

    ```sh
    ❯ sleep 50 &
    [1] 19815
    ❯ jobs
    [1]  + running    sleep 50
    ```

---

36. **gzip** - compress file using the gzip compression protocol named LZ77.

- **gzip \<file_name>** will compress the file and delete original file.

- **gzip -c \<file_name> > \<archive_name>.gz** - the ```-c``` options specifies that output will go to the standard output stream, leaving the original file intact.

- **gzip -k \<file_name>** - the ```-k``` option will original file.
    ```sh
    ❯ gzip -k favColors.txt
    ❯ ls -lh favColo*.*
    -rw-r--r--  1 serhiiolefirenko  staff    75B Feb 23 00:36 favColors.txt
    -rw-r--r--  1 serhiiolefirenko  staff    76B Feb 23 00:36 favColors.txt.gz
    ```

- **gzip -d \<archive_name>** - decompress archive and delete archive.

- **gzip -kv \<file_name>** - show possible decompression rate.
    ```sh
    ❯ gzip -kv favColors.txt
    favColors.txt:       -1.4% -- replaced with favColors.txt.gz
    ```

37. **gunzip** - decompress archive.

38. **tar** - command is used to create an archive, grouping multiple files in a single file. No compression by default.

- **tar -cf archive.tar file1 file2** - create archive with file1 and file2 without compression.

- **tar -xf archive.tar** - to extract files from archive.

- **tar -xf archive.tar -C \<destination_folder>** - extract files to specified destination folder.

- **tar -czf arhive.tar.gz file1 file2*** - create archive with file1 and file2 with compression.

---

39. **nano** - beginner friendly editor. ```Cntr + X``` to exit. ```Cntr + S``` to save.

---

40. **xargs** - used in UNIX shell to convert input from standard input into arguments to a command.

- **cat deadPlayers.txt | xargs rm** - get content from file and put it as arguments to the command after **xargs**.
    ```sh
    ❯ ls
    Player1.txt  Player2.txt  Player4.txt  Player6.txt  Player8.txt
    Player10.txt Player3.txt  Player5.txt  Player7.txt  Player9.txt
    ❯ touch deadPlayers.txt
    ❯ nano deadPlayers.txt
    ❯ cat deadPlayers.txt
    Player1.txt Player3.txt Player5.txt Player7.txt
    ❯ cat deadPlayers.txt | xargs rm
    ❯ ls
    Player10.txt    Player2.txt     Player4.txt     Player6.txt     Player8.txt     Player9.txt     deadPlayers.txt
    ```

---

41. **who** - displays the user logged in to the system.

42. **su** - while you're logged in to the terminal shell with one user, you might have the need to switch to another user. You need to know passowrd of another user.

43. **sudo** - used to run a command as root.

---

44. **passwd** - modify user's password.

- **sudo passwd \<username>** - update password for specified user.

45. **chown** - change file owner and group.

- **chown \<owner> \<file_or_folder>** - should be run with 'sudo'. ```-R``` option change user and group recursively.

- **chown \<owner>:\<group> \<file_or_folder>** - command to update user and group.

<br/>

**Understanding permissions**

<table style="border: 1px solid;">
    <tr>
    <td style="border: 1px solid;">drwxr-xr-x<td>
    </tr>
    <tr>
        <td style="border: 1px solid;">
            File type:<br>
            <strong>-</strong> regular file<br>
            <strong>d</strong> direcotry<br>
            <strong>c</strong> character special file<br>
            <strong>l</strong> symbolic link<br>
        </td>
        <td style="border: 1px solid;">Owner</td>
        <td style="border: 1px solid;">Group</td>
        <td style="border: 1px solid;">World</td>
    </tr>
    <tr>
        <td style="border: 1px solid;">d</td>
        <td style="border: 1px solid;">rwx</td>
        <td style="border: 1px solid;">r-x</td>
        <td style="border: 1px solid;">r-x</td>
    </tr>
</table>

**Permissions:**
- r: file can be read / directory's content can be listed
- w: file can be modified / directory's contestns can be modified (create new files, rename files/folders) but only if the executable attribute is also set.
- x: file can be treated as a program to be executed / allows a directory to be entered or 'cd'ed into
- \-: file cannont be read, modified, or executed depending on the location fo the character / directory contents cannot be shown, modified, or cd'ed into depending on the location of the '-' character.

46. **chmod** - tool to alter permissions

- **chmod mode file** - basic syntax

- **chmod g+w file.txt** - add write permission to group.

- **chmod a-w file.txt** - remove write permission from all.

- **chmod o+r file.txt** - add read permission to world.

- **chmod a+rwx file.txt** - add all permissions to all.