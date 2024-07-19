# Login Info

```
ssh martin@info.mcmaster.ca
```

This gets you into the `head` server, which is called infoserv.  Please do not run jobs on the head.  Instead you can connect to the other processors like this: `rsh info115` (or `rsh info113`, `rsh info114`,...).

You can check how busy a system is using the unix command `top`.  Exit by typing `q`.

# Login Graham.computecanada

```
ssh knedlo@graham.computecanada.ca
```

# VIM editor

to start a new txt file

```
vim FILENAME.txt <ENTER>
```

to open tutorial:

```
vimtutor <ENTER>
```

exit ```<esc> :q! <ENTER>```

save ```<esc> :wq <ENTER>```

## motions in normal mode

```<control> r``` redo 

```<esc>``` normal mode

```/``` followed by a phrase searches FORWARD for the phrase. Then ```n``` to find the next occurrence in the same direction or ```N``` to search in the opposite direction. ```<CTRL-O>``` takes you back to older positions, ```<CTRL-I>``` to newer positions.

```?``` search backward for the phrase

```:g/search/s//replace/g``` find and replace

```:set ic``` 'ignorecase' ignore upper/lower case when searching

```:set is``` 'incsearch' show partial matches for a search phrase

```:set hls``` 'hlsearch' highlight all matching phrases
   
```:set nu``` show line numbers
   
   "no" to switch an option off:   ```:set noic```, ```:set nois```, ```:set nohls```

```%``` while the cursor is on a (,),[,],{, or } goes to its match.

```~``` change case (upper/lower case letters)

```0``` to move on the very beginning of the line 

```$``` to move on the end of the line

```a``` to insert text AFTER the cursor

```b``` move backward a word

```A``` to type appended text after the line 

```c``` change operator

```d``` delete operator

```d$```, ```c$``` to delete, change the end of the line 

```dd```, ```cc``` to delete, change the whole line 

```dw``` or ```de```, ```cw``` or ```ce``` to delete, change a whole word behind cursor 

```<CTRL-G>``` displays your location in the file and the file status.

```gg``` moves to the first line.

```number G```  moves to that line number.
 
```G```  moves to the end of the file.

```H``` move to top of screen

```i``` insert mode before the cursor 

```L``` move to bottom of screen

```p``` pastes text

```r``` replace character

```u``` undo

```U``` undo all changes on a line

```v``` visual mode for marking the text

```x``` to delete a letter

```w``` or ```e``` move 1 word forward

```:s/old/new``` to substitute word "old" by "new" in the same line where is cursor.

```:%/old/new/g``` to substitute every occurrence in the whole file.

```:%/old/new/gc``` to find every occurrence in the whole file, with a prompt whether to substitute or not.

```o``` to open a line BELOW the cursor and start Insert mode.

```O``` to open a line ABOVE the cursor

```R``` replaces mode until  <ESC>  is presse

```y``` operator yanks (copies) text, ```p``` puts (pastes) it.

```:help``` help (also ```:help x```; ```:help v``` etc.)
   
## external commands

```:!``` external command e.g. ```:! ls```

```:w FILENAME``` writes the current Vim file to disk with name FILENAME.

```:r FILENAME``` retrieves disk file FILENAME and puts it below the cursor position.
 
```v```  motion  ```:w FILENAME```  saves the Visually selected lines in file FILENAME.

```:r !ls``` reads the output of the ls command and puts it below the cursor position.

## my vmrc file

open vimrc file:
```
vi ~/.vimrc
```

writing the commands
```
set incsearch
set hls
```

# Unix 
   
## Basic terms and commands
   
bash (vykonavatel textovych prikazu) = comand line interpreter

shell (skorapka, plast)

comand (prikaz) = consists of arguments

argument (argument) = 
   
flag = 

prompt (vyzva) = several characters on the begening of line


`>` = “ send . . . output to `>` . . . ”
   
`>>` = “append/insert . . . output onto `>>` the end of . . . ” 
   
`<` = “take . . . input from `<` . . . ”
 
`|` = pipe = take the output of one command and use it as input for another command
    
`bg` = begin job again
   
`cat` = print the content of a file to the screen

`cat -n` = print the content of a file with number of the output lines, starting at 1

`cd ` \<directory path\> = change a directory
   
`cd` with no argument = go to home directory
   
`chmod [references][operator][modes] filename` = change mode; references = u, g, o, a; operator = +, -, =; modes = r, w, x

`clear` = clean the screen

`Command .` = cancel a command type

`cp original.txt duplicate.txt` = copy = copy file "original" to "duplicate

`du -sh dir1` = how large directory \<dir1\> is

`fg` transfer job from background to foreground

`grep searched_word folder/file name` = search a file
   
`grep --colour=auto searched_word` \<folder/file name\> = search a file highlighted with colour

"home" and "xxx" directory `ls /home /xxx`= view the content of content of home

`kill` \<job name\> or \<number of process\> or \<%order numberof process\> = Kill a job

`logout`, `exit` or `control` + `d` = logout
   
`lpr` = print

`ls` = list files = view the contents of a current directory

`ls -a` list files including hidden files with beginning ., ..
   
`ls -l` detailed list files

`ls -lh` detailed list files

`ls --help` = help about ls

`mkdir` \<directory name\> = make a directory
   
`more` = show partial file contents

`mv` \<directory path\> \<directory pathII\> = moving folder to another folder

`mv` \<folder/file name\> \<folder/file_nameII\> = renaming folder/file

`ps` = view of jobs currently running

`pwd` = print working directory = what directory you are in  

`rm filename` = remove filename

`rm -f filename` = remove a directory 

`rm -rf filename` = remove a file type
   
`rm *` = remove all files!

`rsync` synchonize files between source and a final destination (only the differences between the source and the destination).

```
rsync -axvH --no-g --no-p knedlo@graham.computecanada.ca:/home/knedlo/projects/rrg-ben/knedlo/2023_clivii_largeni_pygmaeus/raw_data/NS.LH00147_0009.003.IDT_i7_91---IDT_i5_91.AMNH17294_male_R*.fastq.gz .
```

`scp` = secure copy. For example from graham.computecanada to google disk: `scp knedlo@graham.computecanada.ca:\<directory1 path\> scp knedlo@graham.computecanada.ca:\<directory2 path\> \<final destination path\> ` 

```
scp knedlo@graham.computecanada.ca:/home/knedlo/projects/rrg-ben/knedlo/gff3_files/XTlongCDS_to_XB_Ssubgenome_plotter.txt knedlo@graham.computecanada.ca:/home/knedlo/projects/rrg-ben/knedlo/gff3_files/XLlongCDS_to_XBgenome_plotter.txt .
```

`less`

`tee`

### keyboard shortcuts
 
\<control\> + `a` = send prompt on the beginning of line

\<control\> + `d` = logout

\<control\> + `e` = send prompt on the end of line

\<control\> + `c` = cancel job, leave emacs

\<control\> + `k` = delete the end of the line
   
\<control\> + `u` = delete the line before the prompt
   
\<control\> + `w` = delete backward to the beginning of the word

\<control\> + `x` = save the emacs file

\<control\> + `z` = stop job temporalily
   
\<option\> + \<Left/Right Arrow\> move the prompt backward/forward one word

### Top

If you want to check the status of the job, do `top`.

To get off the top, do `q`.

To see the full command running on top, do `top` then `c`.

If you just want to look at your top, do `top -u martin`.

### Using Unix Screen

Screen is very useful for running background jobs.

To launch a screen session type `screen -S `\<session name\>.

To exit a screen type `control a, d`.  

To list screen type `screen -ls`.

To reconnect with a screen type `screen -r `\<session name\>.

To kill a screen type `screen -X -S ` \<session name\> ` kill`.

To exit the server type `logout`.

### My bashrc file

Backup the current .bashrc file:

```
cp ~/.bashrc ~/.bashrc.bak
```

open my bashrc file in the vim editor: 

```
vi ~/.bashrc
```

Apply the changes by sourcing the .bashrc file:

```
source ~/.bashrc
```

### Installing trinity

To download the trinity package we typed `Tr`.  This link would have to be updated when an new version becomes available.

To uncompress it, type `tar -zxvf v2.2.0.tar.gz`

Instructions for install are her `https://github.com/trinityrnaseq/trinityrnaseq/wiki/Installing%20Trinity`.

# The data

Once the data were copied over, we uncompressed each file like this:

`tar -xvf Sample_BenEvansBJE3909cDNA_Library.tar`
and
`tar -xvf Sample_BenEvansBJE4168cDNA_Library.tar`

# To empty space in head 1 server, move it and zip it 
To know how large the file is:
 ```
 du -sh *
 ```
To move it to head 4:
```
mv trinityrnaseq-2.2.0/ /4/xue/
```
To create a symbolic link:
```
ln -s /4/xue/trinityrnaseq-2.2.0/ hereistrin
```
To move it back to head 1 from head 4:
```
mv /4/xue/trinityrnaseq-2.2.0/ .
```
To zip files:
```
gzip filename
```
To zip directory: 
```
tar -cvf genome_data.tar genome_data
```
# Sent notice when job is done from the server
```
SOME COMMAND ; echo "this job is done" | mail your_email@gmail.com
```

# To list all the package installed in R
```
ip <- as.data.frame(installed.packages()[,c(1,3:4)])
rownames(ip) <- NULL
ip <- ip[is.na(ip$Priority),1:2,drop=FALSE]
print(ip, row.names=FALSE)
```
