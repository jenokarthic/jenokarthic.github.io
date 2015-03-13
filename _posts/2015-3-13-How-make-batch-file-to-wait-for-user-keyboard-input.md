---
layout: post
title: How to make the BATCH script to wait for user Keyboar Input?
---

While running bat files, if any error occurs, it will vanishes without waiting for the user to review it.  To overcome this issue, we can make the bat file to wait for the user input to terminate the window like getch() is being used in C programming.

To do that,  add the following line at end of the bat file.

```bash
set /p DUMMY=Hit ENTER to continue...
```

Once the batch file is processed, it will wait for your key input to close. 