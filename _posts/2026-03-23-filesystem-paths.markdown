---
layout: post
title:  "Linux 0x00: Filesystem Paths, Absolute and Relative"
date:   2026-03-23 15:25:12 +0500
categories: linux
---

File system in Linux is a `tree` like structure. In this tree the top node is named as `root`.

We can call this `root` as a `directory`. And in the `root directory` there could be so many other directories. 

Likewise, every directory can contain more directories in it.

This root is represented as `/`. As I said earlier root directory can contain other directories, if we want to move from root to another directory or if we want to run a binary file. We can do so by writing it's name. How?

Suppose there exist a `hello-world` binary in the `/` directory. And we want to run it:

```bash
hafizfarhad@pwntheprompt:/$ ls
hello-world bin tmp usr
hafizfarhad@pwntheprompt:/$ /hello-world
```

This is absolute path. Whenever we reference root directory to move in other directories or to execute `elf`. It's called absolute path.

While relative is more of a dependent on present working directory `(pwd)`. Now, let's say we have another file in our home directory `~` named as `hello-world`.

```bash
hafizfarhad@pwntheprompt:~$ ls
hello-world
hafizfarhad@pwntheprompt:~$ ./hello-world
```

Accessing any file or folder (directory) other than referencing `/` directory is relative path.

There are two types of relative path:

**1. Implicit relative path:**

Here, whenever we run `hello-world` It checks some predefined list. And gives error if `hello-world` was not on the list. Here, we don't use any special symbols like current directory (`.`) or parent directory (`..`).

```bash
hafizfarhad@pwntheprompt:~$ hello-world
hello-world: command not found
```

**2. Explicit relative path:**

In explicit relative path, system knows that the program `hello-world` is basically in this current working directory and runs it. How? we use special symbols like `.` or `..`.

```bash
hafizfarhad@pwntheprompt:~$ ./hello-world
```

Thanks for reading `;)`.