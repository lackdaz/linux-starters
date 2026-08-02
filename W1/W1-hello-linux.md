---
author: Seth
date: MMM dd, YYYY - VIVITA
paging: Slide %d / %d
theme: ../theme/theme.json
---

```
~~~toilet --font mono12 -t
LINUX
~~~
```

```
~~~toilet --font mono12 -t
STARTERS
~~~
```

---

# hello-linux

Welcome to BLUR

Linux Tutorial Season 2

Episode 1
---

## Outline (120 mins)

1. Learning Philosophy (5 mins)
1. First boot/login
1. First look (GUI) (30 mins)
    - Start button, installed software
    - Navigation (Software Manager, Preferences, Admin)
    - MS-equivalents
        - Writer
        - Calc
        - Impress
        - Draw
        - Base & Math
    - Go Online - WiFi, web browser
    - File Explorer (FS) - show hidden files

1. First look (Terminal)
    - Set your HOSTNAME
    - CLI Jam! (10 mins)

1. What is Linux? - slides (30 mins)

1. Stretch goals (40 mins)
    - Trivia/Discussion
        - What other reasons to change to Linux
    - How to install software - e.g. browser
    - Install learning slides
    - Watch full video link (53 mins)

- [W1 slides](https://github.com/lackdaz/linux-starters/blob/main/W1/Linux-S01.pptx)

---
## Learning Philosophy
- Slow and steady
-  Peer-to-Peer
- Passion-led
---
## Don't Panic
- Don't worry if you cannot remember every detail
- Don't worry if you don't understand every command
- Repetition helps
- Remember concept, base command, google the details
---
## We have made the hard decisions for you
- What Linux to use
- How to install
- Where to install
More of what, why, how later.
---
## First boot / login
- Plug-in USB flashdrive
- Power-on
- Press ESC.
- - If you missed:
  - Press any key to continue
  - $\color{#AAAA00}{\text{ Shell> }}$ _exit_
- Login: _maker_
- Password: _123456_

---
#
---
## CLI Jam! Install some fun packages in the CLI

### `lolcat`

`cat` but colorful!

Install:  

```
sudo apt install lolcat fortune-mod
```

Usage:  

```
fortune | lolcat
```

Run continuously:  

```
watch -n 5 | fortune | lolcat
```

---

### `asciiquarium`

An ASCII fish aquarium(?) wallpaper

Install:  

```
sudo add-apt-repository ppa:ytvwld/asciiquarium \
&& sudo apt update \
&& sudo apt install asciiquarium
```

Usage:  

```asciiquarium```

---

## `cmatrix`

Run matrix-y wallpaper

Install:  

```
sudo apt install cmatrix
```

Usage:  

```
cmatrix
```

---

### `espeak`

A text-to-speech reader

Install:  

??? (you tell me)

Usage:  

```
espeak -v cy 'Llanfairpwllgwyngyllgogerychwyrndrobwllllantysiliogogogoch'
```

---

## Trivia

> Where can you find Linux? [3 answers]

---

> What do you understand about open-source?

---

> Why are we using Linux Mint?

---
