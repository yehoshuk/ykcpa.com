---
title: How to reset the last cell in an Excel worksheet
pubDate: 06/18/2019
author: "Josh Krupnick"
tags:
  - Excel
  - VBA
description: A quick VBA trick to reset Excel's "last cell" when Ctrl+End jumps too far away from your actual data.
---

After I've added/deleted/moved/copied... basically, done enough work in an Excel worksheet so that when I hit Control-End, Excel goes to a cell far, far away from any of my work, I do the following to reset the "last cell"

#### Hit Control-End to see what Excel considers the last cell before you perform the instructions below.

Press `Alt-F11`

#### This should open the VBA editor

Press `Control-G`

#### This should open a window at the bottom with the title `Immediate`

Type the following in the Immediate window and then press Enter:

`ActiveSheet.UsedRange`

#### Now hit Control-End again and see how Excel jumps upwards and/or leftwards... you've done it!
