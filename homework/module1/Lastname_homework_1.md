# Домашнє завдання №1. Основи Linux і робота в терміналі

## Завдання 1. Базові команди (1 бал)

### Покажи вміст домашнього каталогу
Команда: `cd /home/padav; pwd; ls -la | head -10`  
Результат:  
```
/home/padav
total 28
drwxr-x--- 3 padav padav 4096 Mar 11 12:11 .
drwxr-xr-x 3 root  root  4096 Mar 11 12:04 ..
-rw------- 1 padav padav    5 Mar 11 12:11 .bash_history
-rw-r--r-- 1 padav padav  220 Mar 11 12:04 .bash_logout
-rw-r--r-- 1 padav padav 3771 Mar 11 12:04 .bashrc
drwx------ 2 padav padav 4096 Mar 11 12:04 .cache
-rw-rw-r-- 1 padav padav    0 Apr  7 07:09 .motd_shown
-rw-r--r-- 1 padav padav  807 Mar 11 12:04 .profile
```

### Перейди у каталог Downloads і покажи його вміст
Команда: `mkdir -p /home/padav/Downloads; cd /home/padav/Downloads; pwd; ls`  
Результат:  
```
/home/padav/Downloads
```

### Створи порожній файл (без touch)
Команда: `cd /home/padav/Downloads; > empty.txt; ls`  
Результат:  
```
empty.txt
```

### Переглянь вміст файлу
Команда: `cd /home/padav/Downloads; cat empty.txt`  
Результат: (порожній файл, немає виводу)

### Перейди у домашній каталог абсолютним шляхом
Команда: `cd /home/padav/Downloads; cd /home/padav; pwd`  
Результат:  
```
/home/padav
```

### Перейди у домашній каталог відносним шляхом
Команда: `cd /home/padav/Downloads; cd ..; pwd`  
Результат:  
```
/home/padav
```

## Завдання 2. Робота з документацією (2 бали)

### man ls
Команда: `man ls | head -20`  
Результат:  
```
LS(1)                            User Commands                           LS(1)  

NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about  the FILEs (the current directory by default).  
       Sort entries alphabetically if none of -cftuvSUX nor --sort  is  speci‐  
       fied.

       Mandatory  arguments  to  long  options are mandatory for short options  
       too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
```

### help cd
Команда: `help cd`  
Результат:  
```
cd: cd [-L|[-P [-e]] [-@]] [dir]                                                
    Change the shell working directory.

    Change the current directory to DIR.  The default DIR is the value of the   
    HOME shell variable. If DIR is "-", it is converted to $OLDPWD.

    The variable CDPATH defines the search path for the directory containing    
    DIR.  Alternative directory names in CDPATH are separated by a colon (:).   
    A null directory name is the same as the current directory.  If DIR begins  
    with a slash (/), then CDPATH is not used.

    If the directory is not found, and the shell option `cdable_vars' is set,   
    the word is assumed to be  a variable name.  If that variable has a value,  
    its value is used for DIR.

    Options:
      -L        force symbolic links to be followed: resolve symbolic
                links in DIR after processing instances of `..'
      -P        use the physical directory structure without following
                symbolic links: resolve symbolic links in DIR before
                processing instances of `..'
      -e        if the -P option is supplied, and the current working
                directory cannot be determined successfully, exit with
                a non-zero status
      -@        on systems that support it, present a file with extended        
                attributes as a directory containing the file attributes        

    The default is to follow symbolic links, as if `-L' were specified.
    `..' is processed by removing the immediately previous pathname component   
    back to a slash or the beginning of DIR.

    Exit Status:
    Returns 0 if the directory is changed, and if $PWD is set successfully when 
    -P is used; non-zero otherwise.
```

### man cat
Команда: `man cat | head -20`  
Результат:  
```
NAME
       cat - concatenate files and print on the standard output

SYNOPSIS
       cat [OPTION]... [FILE]...

DESCRIPTION
       Concatenate FILE(s) to standard output.

       With no FILE, or when FILE is -, read standard input.

       -A, --show-all
              equivalent to -vET

       -b, --number-nonblank
              number nonempty output lines, overrides -n

       -e     equivalent to -vE
```

### man man
Команда: `man man | head -20`  
Результат:  
```
man: can't resolve man7/groff_man.7
MAN(1)                        Manual pager utils                        MAN(1)

NAME
       man - an interface to the system reference manuals

SYNOPSIS
       man [man options] [[section] page ...] ...
       man -k [apropos options] regexp ...
       man -K [man options] [section] term ...
       man -f [whatis options] page ...
       man -l [man options] file ...
       man -w|-W [man options] page ...

DESCRIPTION
       man  is  the system's manual pager.  Each page argument given to man is  
       normally the name of a program, utility or function.  The  manual  page  
       associated with each of these arguments is then found and displayed.  A  
       section,  if  provided, will direct man to look only in that section of  
       the manual.  The default action is to search in all  of  the  available  
       sections following a pre-defined order (see DEFAULTS), and to show only
```

### cp --help
Команда: `cp --help | head -20`  
Результат:  
```
  or:  cp [OPTION]... SOURCE... DIRECTORY
  or:  cp [OPTION]... -t DIRECTORY SOURCE...
Copy SOURCE to DEST, or multiple SOURCE(s) to DIRECTORY.

Mandatory arguments to long options are mandatory for short options too.        
  -a, --archive                same as -dR --preserve=all
      --attributes-only        don't copy the file data, just the attributes    
      --backup[=CONTROL]       make a backup of each existing destination file  
  -b                           like --backup but does not accept an argument    
      --copy-contents          copy contents of special files when recursive    
  -d                           same as --no-dereference --preserve=links        
      --debug                  explain how a file is copied.  Implies -v        
  -f, --force                  if an existing destination file cannot be        
                                 opened, remove it and try again (this option   
                                 is ignored when the -n option is also used)    
  -i, --interactive            prompt before overwrite (overrides a previous -n 
                                  option)
  -H                           follow command-line symbolic links in SOURCE     
  -l, --link                   hard link files instead of copying
```

### mv --help
Команда: `mv --help | head -20`  
Результат:  
```
Usage: mv [OPTION]... [-T] SOURCE DEST                                          
  or:  mv [OPTION]... SOURCE... DIRECTORY
  or:  mv [OPTION]... -t DIRECTORY SOURCE...
Rename SOURCE to DEST, or move SOURCE(s) to DIRECTORY.

Mandatory arguments to long options are mandatory for short options too.        
      --backup[=CONTROL]       make a backup of each existing destination file  
  -b                           like --backup but does not accept an argument    
      --debug                  explain how a file is copied.  Implies -v        
  -f, --force                  do not prompt before overwriting
  -i, --interactive            prompt before overwrite
  -n, --no-clobber             do not overwrite an existing file
If you specify more than one of -i, -f, -n, only the final one takes effect.    
      --no-copy                do not copy if renaming fails
      --strip-trailing-slashes  remove any trailing slashes from each SOURCE    
                                 argument
  -S, --suffix=SUFFIX          override the usual backup suffix
  -t, --target-directory=DIRECTORY  move all SOURCE arguments into DIRECTORY    
  -T, --no-target-directory    treat DEST as a normal file
      --update[=UPDATE]            control which existing files are updated;
```

### Питання

Який ключ ls показує приховані файли?  
Відповідь: `-a` або `--all`

Який ключ у cat нумерує рядки?  
Відповідь: `-n` або `--number`

Чим відрізняються man і -help?  
Відповідь: `man` надає детальну сторінку довідки з повним описом команди, її опцій та прикладів використання. `--help` надає коротку допомогу з основними опціями та синтаксисом команди.

## Завдання 3. Міні-сценарій (2 бали)

Сценарій з 8 команд:

1. `cd /tmp` - Перейти в каталог /tmp  
2. `> file.txt` - Створити порожній файл file.txt  
3. `ls` - Переглянути список файлів в /tmp  
4. `cd /home/padav` - Перейти в домашній каталог  
5. `cp /tmp/file.txt .` - Скопіювати файл в домашній каталог  
6. `ls` - Переглянути список файлів в домашньому каталозі  
7. `man ls | head -5` - Переглянути документацію команди ls  
8. `mv file.txt newfile.txt` - Перейменувати файл  
9. `ls` - Переглянути список файлів після перейменування  
10. `cat newfile.txt` - Переглянути вміст файлу  

Цей сценарій використовує тільки команди ls, cd, cat, man, cp, mv.</content>
<parameter name="filePath">d:\file\code\OC\OC HW 1\homework\module1\Lastname_homework_1.md