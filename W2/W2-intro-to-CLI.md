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

- [ ] Play a terminal game
- [ ] encrypt/decrypt stuff
- [ ] Shortcuts - symlinks, aliases, bash scripts

---

## Dependencies for installation

**GO TO THIS URL**:

<https://tinyurl.com/linux-starters>

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

### Question
>
>Q: Can you see the difference?

---

## Basic commands

### `ls` - list

Download this massive sneaky file (134MB) - Press `ctr-e` if in `slides` and wait...

```bash
wget https://bioacousticlib.sgp1.digitaloceanspaces.com/linux/rockyou.txt 
# this downloads the rock.txt from a totally safe place on the internet 
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

`less rockyou.txt`

`pgdown` - to go to next page

`pgup` - to go to previous page

`arrowdown` - to go one line down

`arrowup` - to go one line down

`q` - to exit  

#### Has your password been hacked?

`grep <password> rockyou.txt`

---

## How to find help?

1. `-h` or `--help`
1. `man`
1. `info`

---

## Activity

1. Go to the shire directory and look for all the hidden treasures!

Refer to the cheatsheet in the next slide if get stuck!

---

### Cheatsheet

1. Basic commands
    1. `ls`
        - modes: -a, `-la`, `-lh`, `-lrt`
    1. `cd`
        - `cd -`    # go back
        - `pwd`     # current working directory
    1. Read files
        - `touch`   # create files
        - `xed`     # edit file with GUI
        - `cat`     # read contents of file
        - `head`    # read first n lines of file
        - `tail`    # read last n lines of file
        - `grep`    # filter
        - `less`    # read a portion of (a very big) file
    1. How to find help?
        - `-h` or `--help`
        - `man`
        - `info`

---

What we missed this week:

1. `rm`     # remove
1. `mkdir`  # make directory, or folder
1. `mv`     # moves and renames files

---

## Encoding/decoding of hidden files

to encode:  

```
base64 -i birthday_cake.txt > .secret.b64
# Explanation: `>` replaces contents of (and creates) `.secret.b64`
```

to decode:  

```
base64 -d  .secret.b64 | cat
```

---

## SSH

### Let's a play a snake game

```
ssh snakes.run
```

---
