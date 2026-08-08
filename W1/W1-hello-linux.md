---
author: Seth & Cathy
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
INTRO
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
1. First look (Terminal)
    - Set your HOSTNAME
    - CLI Jam! (10 mins)

1. What is Linux? - slides (30 mins)

1. Stretch goals

- [W1 slides](https://github.com/lackdaz/linux-starters/blob/main/W1/Linux-S01.pptx)

---
## Learning Philosophy
- Slow and steady
- Peer-to-Peer
- Passion-led
---
## Don't Panic, Just graze
- Don't worry if you cannot remember every detail
- Don't worry if you don't understand every command
- Repetition helps
- Remember concept, base command, google the details
- Ask for help
---
## We have made the hard decisions for you
- What Linux to use
- How to install
- Where to install
More of what, why, how later.
---
## First boot / login
- On the USB flashdrive, write down:
  - Your name (e.g. Minty)
  - Laptop name (e.g. blur001)
- Plug-in USB flashdrive
- **Leave the USB flashdrive plugged at all times**
- Power-on
- Press ESC.
  - If you missed:
  - Press any key to continue
  - $\color{#AAAA00}{\text{Shell> }}$ _exit_
  - <font color="#AAAA00">Shell> </font> _exit_
- Select "Boot Menu", press ENTER
- Select "USB: ... ", press ENTER
- Wait for a few minutes for Linux Mint to boot up
- Login: _maker_
- Password: _123456_
- DO NOT CHANGE THIS PASSWORD

---
## First look (GUI)
- Start button, installed software
- Navigation (Software Manager, Preferences, Admin)
- MS-equivalents
  - Writer
  - Calc
  - Impress
   - Draw
   - Base & Math
- Go Online - WiFi, web browser
- File Explorer (Files)
---
## First look (CLI)
CLI = Command Line Interface
aka Terminal
- Open Terminal
- Set your machine hostname
  ```
  sudo hostname blur___
  hostname
  ```
  - e.g. _sudo hostname blur001_

---
```
~~~toilet --font mono12 -t
CLI JAM!!!
~~~
```
---
## CLI Jam! Install some fun packages in the CLI
Let's try out some command lines!

### `ls`
- ```ls``` list files and directories
- ```ls -al``` list All hidden files with detaiLs  
---
### `cd`
- ```cd``` change current directory
- ```cd /``` go to / root directory
- ```ls -al``` list All with detaiLs
- ```cd``` go to your home directory
---

### `fortune`

`fortune` generate words of wisdom

Install:  

```
sudo apt install fortune-mod
```

Usage:  

```
fortune
```

---
### `lolcat`

`cat` but colorful!

Install:  

```
sudo apt install lolcat
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
sudo add-apt-repository ppa:ytvwld/asciiquarium
sudo apt update
sudo apt install asciiquarium
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
## What is Linux?
- [W1 slides](https://github.com/lackdaz/linux-starters/blob/main/W1/Linux-S01.pptx)
---
## Linux Starter Git resource
### `git`

Install:  
```
sudo apt install git
```
Usage:  

```
cd
git clone https://github.com/lackdaz/linux-starters.git
ls linux-starters
```

This contains the slides and hands-on for all 4 sessions.

---
## Trivia

> Where can you find Linux? [3 answers]

---

> What do you understand about open-source?

---

> Why are we using Linux Mint?

---
## Discussion
    - What other reasons to change to Linux
    - How to install software - e.g. browser
    - Install learning slides
    - Watch full video link (53 mins)


---
