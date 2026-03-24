---
layout: post
title:  "Linux 0x00: Filesystem Paths, Absolute and Relative"
date:   2026-03-23 15:25:12 +0500
categories: linux
---

File system in linux is a `tree` structure. In this tree the top is named as `root`.

We can call this `root` as a `directory`. And in the `root directory` there could be so many other directories. 

Likewise every directory can contain more directories in it.

This root is repersented as `/`. As said earlier root directory can contain other directories, if we want to move from root to another directory. We can do so by writing its name. 

Suppose there exist a `hello-world` binary in the `/` directory if we want to run it we can simply write:

```bash
hafizfarhad@pwntheprompt:~$ ls
hello-world
hafizfarhad@pwntheprompt:~$ /hello-world
```

This is absolute file path. Whenever we reference root directory to move in other directories or to execute `elf`. It's called absolute path.

While relative is more of a dependent on present working directory `(pwd)`. 

```bash
hafizfarhad@pwntheprompt:~$ ls
hello-world
hafizfarhad@pwntheprompt:~$ ./hello-world
```

Accessing any file or folder (directory) other than referencing `root` directory is relative file path.

There are two types of relative file path

1. implicit relative path

in implicit if there are two hello-world programs: one by system itself and the one we wrote. Now system might get confused and give error like `bash: run: command not found`. The reason is simple linux is some predefined list and if it doesnt find program in it. It doesnt execute it.

```bash
hafizfarhad@pwntheprompt:~$ hello-world
```

2. explicit relative path

While in explicit path system knows that the program hello-world is basically in this directory and runs it. Hence, we use explicit.

```bash
hafizfarhad@pwntheprompt:~$ ./hello-world
```