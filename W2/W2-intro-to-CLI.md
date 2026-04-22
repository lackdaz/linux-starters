---
author: Seth
date: MMM dd, YYYY - NLB
paging: Slide %d / %d
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

## Learning objectives

- [ ] What is the CLI?
- [ ] Terminal - First Look
- [ ] Basic Commands
- [ ] How to install packages
- [ ] Super commands
- [ ] File Editor(s)

## Activity

1. SSH
1. Scavenger game!

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

<<<<<<< Updated upstream
=======
```
>>>>>>> Stashed changes
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
