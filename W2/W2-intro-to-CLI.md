---
author: Seth
date: MMM dd, YYYY - NLB
paging: Slide %d / %d
---

# Intro to Command Line (CLI)

## Agenda

1. What is the CLI (video)?
    - What is the CLI (Our version)? - cue Harry Potter
    - Axiom - Grazing
1. Terminal - first look
1. Basic commands
    1. `ls`
        - modes: -a, `-la`, `-lh`, `-lrt`
    1. `cd`
        - `tab` is your best friend
        - `cd -` - 'gostan'
    1. Read files
        - `cat`
        - `head`
        - `tail`
        - `less`
    1. How to find help?
        - `-h` or `--help`
        - `man`
        - `info`

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
