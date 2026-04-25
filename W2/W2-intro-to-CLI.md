---
author: Seth
date: MMM dd, YYYY - VIVITA
paging: Slide %d / %d
theme: ../theme/theme.json
---

```
~~~toilet --font mono12 -t
INTRO
~~~
```

```
~~~toilet --font mono12 -t
TO CLI
~~~
```

---

# Intro to Command Line (CLI)

## Outline

1. What is the CLI (video)?
    - What is the CLI (Our version)? - cue Harry Potter
    - Axiom - Grazing


1. Terminal - first look
1. Basic commands
    1. `ls`
        - modes: -a, `-la`, `-lh`, `-lrt`
    1. `cd` - where are you
        - `tab` is your best friend
        - `cd -` - 'gostan'
        - `pwd`
    1. Read files
        - `touch`
        - `xed`
        - `cat`
        - `head`
        - `tail`
        - `grep`
        - `less`
    1. How to find help?
        - `-h` or `--help`
        - `man`
        - `info`

---

## Agenda

## Install slides

- [ ] Installing `slides`
- [ ] Cloning the linux-starters repository

## Learning objectives

- [ ] What is the CLI?
- [ ] Terminal - First Look
- [ ] Basic Commands
- [ ] How to install packages
- [ ] Super commands
- [ ] File Editor(s)

## Stretch goals

- [ ] Shortcuts - symlinks, aliases, bash scripts
- [ ] Code/decode stuff
- [ ] Play a terminal game

---

## Dependencies for installation

**GO TO THIS URL**: 

https://tinyurl.com/linux-starters

First steps in the CLI:

1. Update the APT repositories:  

```
sudo apt update
```

1. Install git and other dependencies.  

```
sudo apt install git toilet golang-go libgraph-easy-perl plantuml
``` 
and press `y`

`libgraph-easy-perl` is for `graph-easy`.
`graphviz` is `plantuml`.

1. Add GO to path and source it

```
echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> ~/.bashrc && source ~/.bashrc
```
---

## Installing `slides`

1. Download the slides repository.  

```
git clone https://github.com/maaslalani/slides
```


1. Access the code repository, make from source and compile the binary  

```
cd slides
```  

```
go install
```

1. Check if slides work:  

```
slides
```

press `q` to exit

---

## Cloning linux-starters

1. Download the code repository  

```
git clone https://github.com/lackdaz/linux-starters
```

1. Go into the directory for the week (for example, W1 for week 1).  

```
cd linux-starters
```

```
cd W1
```

And now we are ready for the class! 

And you just used `git` for the first-time!

---

## What is the CLI

### GUI vs CLI

<https://www.youtube.com/watch?v=w9u0d4C95Zs>

### Why CLI?

<https://www.youtube.com/watch?v=Q1dwzi5DKio&t=82s>


---

## Terminal - First Look

### The "OG" Shell `sh`
- `sh`  

>$ 

### Bash (`B`ourn `A`gain `Sh`ell)

- `bash`

>maker@linux101:~$ 

### Other shells
- `fish`  (`F`riendly `I`nteractive `Sh`ell)  

>maker@linux101 ~>


### Godmode

`sudo su` # drops into superuser mode

>root@linux101:/home/maker#


### Question!
>Q: Can you see the difference?

---

## Basic commands
### `ls` - list

Download this massive sneaky file (134MB) - Press `ctr-e` if in `slides`
```
wget https://bioacousticlib.sgp1.digitaloceanspaces.com/linux/rockyou.txt 
# this downloads the rock.txt from a place on the internet 
```

#### List current directory

```bash
ls . 
```
---

#### hidden files

```bash
ls -la .
# list all (hidden) files
```

```bash
ls -lah .
# list hidden files with human-readable size format
```

---

#### sort by time 

```bash
ls -lt .
# list file details sorted by time (descending)
```

```bash
ls -lrt .
# list file details sorted by time (ascending)
```

---

### `cd` - change directory

#### `There and back again`

1. ```cd shire```

> maker@linux101:~/linux-starters/W2/shire$

1. ```cd mordor```

> maker@linux101:~/linux-starters/W2/shire/mordor$

Oops this looks dangerous, let's go back quickly!

1. ```cd -``` 

> Q: What did that do?
> Q: Where are we now?

---

1. ```ls```

you should see... `mordor` and `rivendell`  

let's go to `rivendell`! But let's auto-complete ... the rest of the unexpected journey
> maker@linux101:~/linux-starters/W2/shire$

1. ```cd r```, then press `tab` like ```cd r<tab>```  

>Q: Wow! how did that work?

1. Now press `enter` and `ls`

>Q: Where did you end up?

1. Let's follow our heroes to the end! (self-learning)

>Q: Where is the final destination?

---

Okay phew! What a long journey, now where am I?

### `pwd` - present working directory (where am I?)

```bash
pwd
```
> /home/maker/linux-starters/W2/shire/rivendell/misty_mountains/mirkwood/laketown/lonely_mountain

> Q: How do I go back to the Shire?

### `cd ..` - let's go up

```
cd ../../.. and so and and so forth
```

This looks confusing so let's try something else

---

### Going back to a shortcut to $HOME

```
cd
```

OR

```
cd ~
```

> Q: How do we get back to `W2`?

---
## Create (empty) files

### `touch` - How to forge an empty magic ring

```bash
touch magic_ring
# note: its empty
```

---

## Edit files

### `xed` - inscribe your file (I mean, magic ring)

```xed magic_ring```

OR

```bash
echo "one ring to rule them all" > magic_ring
```

```bash
cat magic_ring # we'll get to this in the next slide
```

Other types: `nano`, `vim`, `xedit`


---

## Read file contents

### `cat` - concatenate

### read the one-ring (file)

```bash
cat one_ring # read the one-ring
```

---


```bash
cat one_ring # reads the one-ring
echo "" # creates space between output
```
<!-- spacer -->

show first n lines
```bash
head -n 2 one_ring
```

show last n lintes
```bash
tail -n 2 one_ring
```

---
## Read file contents
### `grep` - global regular expression print (sigh) -> let's call it a line filter

```bash
grep ring one_ring
```

note: `grep` is very powerful - as powerful as gandalf. Tell us next time what you've done with `grep`

---
## Read file contents
### `less` 

`less rockyou.txt`. 

`pgdown` - to go to next page. 

`pgup` - to go to previous page.  

`arrowdown` - to go one line down.  

`arrowup` - to go one line down.  

`q` - to exit.  

#### Has your password been hacked?

`grep <password> rockyou.txt`

---

## How to find help?

1. `-h` or `--help`
1. `man`
1. `info`

---


## Activity

---

1. SSH 

---

## What is the CLI?

> A command-line interface (CLI), also known as a command-line shell is a means of interacting with software via commands – each formatted as a line of text. Command-line interfaces emerged in the mid-1960s, on computer terminals, as an interactive and more user-friendly alternative to the non-interactive mode available with punched cards
---

## Terminal - First Look

(show gif with the incantations)

---

## Basic Commands

---
    1. How to update and install packages?
        - `sudo apt update`
        - `sudo apt install neofetch`
            - stretch goal: install `uwufetch`
        - `sudo apt install htop`
        - how to check system/disk usage - `df -h`
        - how to check directory/file size - `du -sh *`
 
    1. Super-commands
        - Pipe - `|`
        - Search for matching text - `grep`
        - `history`

    1. File editor (very controversial)
        - `nano` vs `vim`
        - GUI-based text editors: `xed`
        - How to copy and paste
        - Change your hostname - `sudo xed /etc/hostname`

---

---

1. SSH (Without networking)
        -

    1. SSH Scavenging game
        - Instructions for game:
            - `cat [filename] >> ~/answers/[your-name].txt`
            - TODO: figure this out
        - ASCII art generator - `chafa`
        - `curl -s "$(cat [your-name].txt)" | chafa -c none --symbols=ascii`

    1. Stretch goals
        - Check out `fish`
        - Symlinks - `ln -s`
        - change mode - `chmod -x`

---

<!-- ~~~graph-easy --as=boxart
[ A ] - to -> [ B ]
~~~ -->
```
~~~graph-easy --as=boxart
[ A ] - to -> [ B ]
~~~
```

```
~~~plantuml -utxt -pipe
@startuml
A --> B: to
@enduml
~~~
```

---

```bash
echo "hello world"
```

---

(sponge needs `moreutils`)

script -q test.txt koba --color ~/Downloads/gyarados.png --scale=0.2 && tail -n +5 test.txt | sponge test.txt

```bash
script -q test.txt koba --color ~/Downloads/gyarados.png --scale=0.2 && tail -n +5 test.txt | sponge test.txt
```

---

```bash
cat test.txt
```
