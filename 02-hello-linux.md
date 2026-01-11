---
author: Seth
date: MMM dd, YYYY - NLB
paging: Slide %d / %d
---


# hello-linux

Watch me fumble to get Linux to

## Everything is markdown

In fact, this entire presentation is a markdown file.

---

## Everything happens in your terminal

Create slides and present them without ever leaving your terminal.

---

## Code execution

```go
package main

import "fmt"

func main() {
  fmt.Println("Execute code directly inside the slides")
}
```

---

author: Gopher
date: MMMM dd, YYYY
paging: Slide %d / %d
---

You can execute code inside your slides by pressing `<C-e>`,
the output of your command will be displayed at the end of the current slide.

---

## Pre-process slides

You can add a code block with three tildes (`~`) and write a command to run *before* displaying
the slides, the text inside the code block will be passed as `stdin` to the command
and the code block will be replaced with the `stdout` of the command.

The above will be pre-processed to look like:

┌───┐  to   ┌───┐
│ A │ ────> │ B │
└───┘       └───┘

For security reasons, you must pass a file that has execution permissions
for the slides to be pre-processed. You can use `chmod` to add these permissions.

```bash
chmod +x file.md
```
