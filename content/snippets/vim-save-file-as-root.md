+++
author = "Ramz"
categories = ["snippets", "vim"]
date = "2016-10-18T19:05:07+10:00"
draft = false
title = "Save a file as root user in Vim"
description = "Save a file as root user in vim"
type = "post"
+++

---
Almost every time i forget to open vim as sudo user, that are supposed to be edited by root and make changes. And finally when saving you see one of the most dreaded message “readonly option is set (add ! to override)”.




To save the file without losing all the editing that you have done use the following command

```
:w !sudo tee %
```
