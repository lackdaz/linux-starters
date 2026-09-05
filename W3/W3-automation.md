---
author: Seth
date: MMM dd, YYYY - VIVITA
paging: Slide %d / %d
theme: ../theme/theme.json
---


```
~~~toilet --font mono9 -t
INTRO TO
~~~
```

```
~~~toilet --font mono9 -t
AUTOMATION
~~~
```
---

## Housekeeping - Getting repo updates...and learning a little about __git__

If you have made changes to your code:  
1. go to the project repository root `~/linux-starters`
1. Git stash your changes:  
```
git add .
git stash
```
1. Get latest code changes:  
```
git pull origin main
```
1. Move your changes back:  
```
git stash pop
```

If you are lazy and want to just run all of this in one command, make sure you `chmod +x W3-automation.md` and press `ctr+e`:  

```bash
cd ~/linux-starters
git add .
git stash
git pull origin main
git stash pop
```

And you're ready for the class!

---

## Dependencies ...

- [ ] Install `vim`

## Learning objectives
- [ ] Refresher: `find` Cinderella's shoes
    - Things we missed last week: `rm`, `mkdir`, `mv`, `chmod`
- [ ] `shell-scripting` - chain commands together
- [ ] `cron` - automate your commands
- [ ] `ssh` - move between computers

## Stretch goals
- [ ] Exercises

## Discussion
- Homework / what are we going to do next week
---

## Install `vim`

A powerful text-edit, arch-nemesis of `nano`

```
sudo apt install -y vim
```

---

## Just one more powerful command: `find`

### `find` Cinderella's shoes

```bash
find . -iname "*prince*"
```

```bash
find . -iname "*prince"
```

```bash
find . -iname "prince*"
```

> Q: What does * do?
> Q: What does -i in -iname do?

---

## Introducing wildcards (*)

```bash
ls *
```

```bash
ls *.md
```

__Note: You will use this a lot__


---

## `find` Cinderella's shoes - Activity time!

```
find . -iname "*prince*"
```

> Q: where are Cinderella's shoes?
> Q: Can you find all the hidden items at once in the shire (W2) ?

---

## `grep` The supercommand that looks *into* files

Find a filename with `find` and `|`:
```
find . | grep <pattern>
```

Find a pattern within a file in the current directory:
```
grep -rIl <pattern> .
```

| Flag | Character   | Meaning                     |
|------|-------------|-----------------------------|
| `-l` | lowercase L | list filenames only         |
| `-L` | capital L   | list files that don't match |
| `-I` | capital i   | ignore binary files         |
| `-i` | lowercase i | case-insensitive            |

> How is this different from find?
> What is this used for?

---

## More commands: `cp` ,`mv`, `rm`

### `cp` - copy files
```
cp castle/prince_charming .
```

### `mv` - rename and move files
```
mv prince_charming prince_annoying
```

### `rm` - remove files
```
rm prince_annoying
```

---

```
~~~toilet --font mono9 -t
SCRIPTING
~~~
```
---

```
~~~graph-easy --as=boxart
graph { label: The evolution of UNIX Commands; }
( [command one], [command two], [command three] ) { flow: down; }
( bash script: [C1]  { flow: down; } -- OK --> [C2] { flow: down; } -- OK --> [C3] ) 
( cron: [bash script] { flow:down; } -- wait --> [at 12am] -- execute --> [bash script] { flow:down; } ) 

[command one] ==> { flow: left; } [C1]  == automate ==> [bash script]
[command two] ==> { flow: left; } [C2]
[command three] { flow: up; } ==> { flow: left; } [C3]
~~~
```
---

```
~~~graph-easy --as=boxart
graph { flow: east; }

  [ n1 ] { label: "git add .\ngit stash"; align: left; }
  [ n2 ] { label: "git pull origin main"; align: left; }
  [ n3 ] { label: "git stash pop"; align: left; }

( update.sh:
  [ script ] { label: "\#!/usr/bin/bash\ngit stash\ngit pull origin main\ngit add .\ngit commit -m \"$1\"\ngit stash pop"; align: left; }
)

[n3][n2][n1] -> [ script ]
~~~
```

## Two golden rules of a script:
1. shebang (`#!/bin/bash` as the first line)
1. give it executable permissions (`chmod +x`)
---

## Shell-scripting

### Create your first bash script

1 .Create your empty file  

```
touch reminder.sh
```

1. start with a shebang at the start of the file (#!):   

`#!/bin/bash`

1. Type a command after the shebang, e.g.:  

```
echo "please go home now"
espeak "please go home now"
```

1. Make the file executable:  

```
chmod +x reminder.sh
```

1. Execute the file:  

```bash
./reminder.sh
```

Note: all file paths are relative to where you run the file!

### Cheatsheet

- `crontab -e`  
in `vim`:  
- `i`     - to edit/insert
- `ESC`   - to escape out of edit mode
- `:wq`   - to save changes
- `:q!`   - quit without saving
---

## `cron`: scheduled bash scripts
a time-based job scheduler that automatically runs scripts or commands at specific intervals, such as daily backups, system maintenance, or scheduled alerts.  

How do you run a bash script when you want it, e.g. 
1. Feed your fish every day at 7am and 7pm
1. Every school/work day to wake you up at 7am


> Note: what does echo do?

---

### Exercise! - do a reminder for Cinderella to go home before midnight

Create a bash script to tell you the reminder:

Select default edit for `cron` (first-time only):
```
select-editor
```

and choose `vim` (basic). Choose `nano` if are familiar with it.

Open crontab:  
```
crontab -e
```

If this is your first-time opening cron, select `vim` (option 2)

### Cheatsheet

- `crontab -e`  
in `vim`:  
- `i`     - to edit/insert
- `ESC`   - to escape out of edit mode
- `:wq`   - to save changes
- `:q!`   - quit without saving

### Steps:
1. `crontab -e`

---
## Answer

This is a helper if `reminder.sh` was not created properly
```bash
touch reminder.sh
echo "#!/bin/bash" > reminder.sh
echo 'espeak -s 40 "please go home before midnight!"' >> reminder.sh
chmod +x reminder.sh
./reminder.sh
```

---

## How to use cron?
To define the time you can provide concrete values for
- minute (m)
- hour (h)
- day of month (dom)
- month (mon),
- day of week (dow)
or use '*' in these fields (for 'any').

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|----------------------------------|
| * | * | *   | *   | *   | `/path/to/your/script.sh` |

### Every 10 mins

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|----------------------------------|
| */10 | * | *   | *   | *   | `/path/to/your/script.sh` |

### Every day at 3PM

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|----------------------------------|
| 0 |15 | *   | *   | *   | `/path/to/your/script.sh` |


### Every Mon at 3PM

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|----------------------------------|
| 0 |15 | *   | *   | 1   | `/path/to/your/script.sh` |

---

### Every Cathy's birthday

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|-------------------------------------------------------|
| 0 | 0 | 25   | 4  | *   | `/path/to/secret-birthday-wish.sh` |

[More practice](https://crontab.guru/)

--- 

---

### Exercise: Ask Cinderella to go home + cron

Let's do it together now!

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|-------------------------------------------------------|
|30| 23 |  *  |  *  |  *  | `~/linux-starters/W3/reminder.sh`  |

### Cheatsheet

- `crontab -e`  
in `vim`:  
- `i`     - to edit/insert
- `ESC`   - to escape out of edit mode
- `:wq`   - to save changes
- `:q!`   - quit without saving

### Steps:
1. create the file `reminder.sh`
1. start with the shebang
1. write the reminder: `espeak "please go home now"`
1. give the file permissions to run as a script:
    ```
    chmod +x reminder.sh
    ```
1. instruct `cron` when to run the file and where:
    ```
    crontab -e
    ```

---


### Planet of the Lamp-lighter in the Little Prince

In The Little Prince, he visits a tiny planet where there was only enough room for a street lamp and the Lamp-lighter. 
Because of how small the planet is, a day only last lasts 2 mins* and the Lamp-lighter lights and puts out the lamp every other minute.

The little prince asks, "why have you put out your lamp?"

"Those are the orders. Good evening.", replies the Lamp-lighter.

"I do not understand.", said the little prince.

The lamplighter replies, "There is nothing to understand, orders are orders. Good morning."

But then he explains, "I follow a terrible profession. In the old days, it was reasonable. I put the lamp out in the morning, and in the evening I lighted it again. I had the rest of the day for relaxation and the rest of the night for sleep.

The little prince then asks, "And the orders have been changed since that time?"

"The orders have not changed", said the Lamp-lighter. "That is the tragedy. From year-to-tear the planet has turned more rapidly and the orders have not changed!". "Then - the planet now turns every 2 minutes*, and I no longer have any time for rest!"

[storybook narration - ](https://youtu.be/jMTMPMjX3-4?si=AWiZoLO6NvUrwoAj&t=4242)

---
##  Can you help the Lamp-lighter greet the little Prince --- every min?
1. "Good morning" at every odd minute
1. "Good evening" at every even minute

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|-------------------------------------------------------|
| ? | ? |  ?  |  ?  |  ?  | `~/linux-starters/W3/good_morning.sh`  |
| ? | ? |  ?  |  ?  |  ?  | `~/linux-starters/W3/good_evening.sh`  |

For those of you that are quick:  

>> How do you disable the cronjob?
>> What is an allegory? 
>> What/who do you think the Lamp-lighter represents?
>> What has this got to do with automation?

### Cheatsheet

- `crontab -e`  
in `vim`:  
- `i`     - to edit/insert
- `ESC`   - to escape out of edit mode
- `:wq`   - to save changes
- `:q!`   - quit without saving

---

## Answer

| m | h | dom | mon | dow | command |
|---|---|-----|-----|-----|-------------------------------------------------------|
| 1-59/2 | * |  *  |  *  |  *  | `~/linux-starters/W3/good_morning.sh`  |
| 0-58/2| * |  *  |  *  |  *  | `~/linux-starters/W3/good_evening.sh`  |
| # * | * |  *  |  *  |  *  | `~/linux-starters/W3/disabled.sh`  |

>> Note: Adding a # comments out the line. Disabling the line from being "activated". This is also how we write notes to ourselves/others.

This is a hard one! Phew. Now the Lamp-lighter hopefully gets some rest.

>> Remember to disable or delete cronjobs that is not being used!

---

## Bonus - SSH

```
~~~graph-easy --as=boxart
graph { label: "-- SSH --"; }
(You:[ (client) ], [ your bash ], [ your cron ]) ---> (Server:[ (remote) ], [ server's bash ], [ server's cron ]) 
[ (client) ] { border: none; } -- SSH --> [ (remote) ] { border: none; }
[ your bash ] <.> [ server's bash ]
[ your cron ] <.> [ server's cron ]
~~~
```
---

## Bonus - SSH

Now we're going to try to politely access each other's computers. Find a pairing partner!

let's set things up first. We need two packages - `openssh-client` and `openssh-server`

>> How do you install these?

Now create an ssh-key:  
```
ssh-keygen
```
> Note: Do not put a password. Can you take a guess why?

After creating an SSH key-pair.. note that `~/.ssh/` now has two files, called:  
- `id_ed25519`
- `id_ed25519.pub`  

It is not important to understand what these do now. But you can watch this [Diffie-Hellman Key Exchange](https://www.youtube.com/watch?v=YEBfamv-_do&t=151s) video if you really want to get into cryptography!

Just know that you should never share the `id_ed25519` (without the `.pub`) ever! `id_ed25519.pub` can be shared freely with anyone without consequence.

---

## Remote Access

To make things a little simpler:
```
ssh-copy-id maker@[hostname].local
```
where hostname is `blur001`, `blur002` ... etc

This copies your key into the computer and allows you passwordless access in the future. Think of it as your fingerprint.

Now let's try access:
```
ssh maker@[hostname].local
```

> What do you see?
---

## Remote Access

Now you're in someone's computer, what do you do?

Say "Hi!" of course!

>> How can you do that?

Now exit from the `ssh` session.
type:  
```
exit
```
And you should be back to your computer.

---

## Remote-pair Activity Time

### The task here is to:  
On your computer (client):
1. Create a file named after an animal (`dog`, `cat`, `hamster`, `fish` etc), anywhere inside the `linux-starters project folder` - e.g. `W0`, `W1`, `mirkwood`, anywhere!
1. Inside that file, write the name of your pet or make a proclamation, e.g. "I am Duke Pepperton of Huskia" or "I am whiskers and I like smelly cheese". 
1. Tell your partner what animal to look for.

On the remote/partner's computer (server):
1.  `ssh` into your partner's computer, find that pet and proclaim his/her/their name, e.g. `espeak "I found Lord Pepperton of Huskia"`

> Note: do you still remember how to find something?

---

## Internet Folklore:

1. `inform-my-spouse.sh`  
    Sends a text message "late at work" to her spouse (apparently). Automatically picks reasons from an array of strings, randomly. Runs inside a cron-job. The job fires if there are active SSH-sessions on the server after 9pm with her login.    

1. `john-silly.sh`
    scans the inbox for emails from "john" (a DBA at our clients). Looks for keywords like "help", "trouble", "sorry" etc. If keywords are found - the script SSHes into the clients server and rolls back the staging database to the latest backup. Then sends a reply "no worries mate, be careful next time".  

1. `hangover.sh` 
    another cron-job that is set to specific dates. Sends automated emails like "not feeling well/gonna work from home" etc. Adds a random "reason" from another predefined array of strings. Fires if there are no interactive sessions on the server at 8:45am.  

1. `brew-coffee.sh` 
    this one waits exactly 17 seconds (!), then opens a telnet session to our coffee-machine (we had no frikin idea the coffee machine is on the network, runs linux and has a TCP socket up and running) and sends something like sys brew. Turns out this thing starts brewing a mid-sized half-caf latte and waits another 24 (!) seconds before pouring it into a cup. The timing is exactly how long it takes to walk to the machine from the dudes desk.

Source: https://github.com/NARKOZ/hacker-scripts

---

## Let's Discuss

Do you have any questions about scripting/automation/SSH?
---

## Discussion: Next week

> Explore and find a software/trick that runs on Linux and share it with the class

The org team can help you set it up 

## Suggestions
1. Some 3D modeling tools
1. Related to the makerspace?
1. Command-line wizardry
1. Games!
1. Out of ideas? Check 
[awesome-linux](https://github.com/luong-komorebi/Awesome-Linux-Software)


---
