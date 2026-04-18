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

Run 1:

Participants:

1. Hisham (BYOL)
1. Francis (BYOL)
1. Alexander (BYOL)
1. Evander (BYOL)
1. Kim (BYOL, setup)
1. Hasan
1. Hidayah
1. Neo
1. Viya
1. George
1. Zephan
1. Trevis

---

## Foreword

Many, many thanks to:

1. **VIVITA** for the venue and equipment sponsorship
1. Johan for the donation of laptops
1. Cathy for the OG inspiration for the class
1. Neo for being the installation maestro and helping to get the dual-boot provisioned

---

## Outline (120 mins)

1. Learning Axioms (10 mins)
1. What is Linux? - slides (30 mins)
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

    - CLI Jam! (10 mins)

1. Stretch goals (40 mins)
    - Trivia/Discussion
        - What other reasons to change to Linux
    - How to install software - e.g. browser
    - Install learning slides
    - Watch full video link (53 mins)

- [W1 slides](https://github.com/lackdaz/linux-starters/blob/main/W1/Linux-S01.pptx)

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
