---
author: Seth
date: MMM dd, YYYY - VIVITA
paging: Slide %d / %d
theme: ../theme/theme.json
---

# Before we start

1. Always make sure that this file is executable:

```bash
chmod +x W0-setup.md
```

press `ctr-e` to run the code block

---

# Provision for the Linux Class

## Outline

There are primarily 3 ways of getting Linux to a computer:

1. Wipe and install (easiest, not covered here)
1. Dual-boot (Linux installed after WinOS)
1. USB-boot (Linux on a USB stick)

```
~~~graph-easy --as=boxart
graph { label: "── Method 1: Wipe and install ──"; }
( Computer: [ WinOS ] -- wiped --> [ Linux ] )
~~~
```

---

```
~~~graph-easy --as=boxart
graph { label: "── Method 2: Dual-boot: Linux installed after WinOS ──"; }
(Computer:[ WinOS | Linux ]) 
~~~
```

```
~~~graph-easy --as=boxart
graph { label: "── Method 3: USB Boot ──"; }
(Computer:[ WinOS],[Linux ]) (USB: [ Linux II ])  [ Linux ] <-> [  Linux II ]
~~~
```

---

- All of which needs a USB bootable. This is a once-off bootloader.

# 1. Getting the USB bootable sorted out

Writing the USB bootable

**Live-boot**: test environment in Linux Mint - non-persistent and meant to install Linux

**USB-bootable**: needs to be installed, persistent

***

1. Write Linux to a USB Live-boot using Etcher(5 mins)

1. Get into your BIOS and disable (15 mins):
    - secure-boot
    - fast-boot
    - Rapid Storage Technology (RST)
    - Change boot order
1. Write the USB bootable - follow the steps
1. Pause when you are asked to format your thumb drive - **!!! wait for us to verify !!!**
1. Write the thumb-drive (7 min)
1. Listen to a brief history of Linux, why linux?
1. Restart the OS

~end~

---

## Let's install the slides

First steps in the CLI:

1. Update the APT repositories:  

```sudo apt update```

1. Install git and other dependencies.  

```sudo apt install git toilet golang-go libgraph-easy-perl plantuml``` and press `y`

`libgraph-easy-perl` is for `graph-easy`.
`graphviz` is `plantuml`.

1. Add GO to path and source it!

```echo 'export PATH="$PATH:$(go env GOPATH)/bin"' >> ~/.bashrc && source ~/.bashrc```

1. Download the slides repository.  

```git clone https://github.com/maaslalani/slides```

1. Access the code repository, make from source and compile the binary  

```cd slides```  

```go install```

---

1. Check if slides work:  

```slides```

press `q` to exit

1. Download the code repository  

```git clone https://github.com/lackdaz/linux-starters```

1. Go into the directory for the week (for example, W1 for week 1).  
```cd linux-starters```

```cd W1```

And now we are ready for the class!

---
