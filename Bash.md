# Bash

## Linux Operating Systems
Linux is a popular choice for a server environment. There are a variety of open-source distributions each with a large community of hobbyists and professionals supporting them. Unique development tools are widespread and simple to install, use, and maintain. And most distributions are very capable without the resource overhead of a graphical desktop user interface.

## Unix Philosophy
1. Make each program do one thing well. To do a new job, build afresh rather than complicate old programs by adding new “features”.
2. Expect the output of every program to become the input to another, as yet unknown, program. Don’t clutter output with extraneous information. Avoid stringently columnar or binary input formats. Don’t insist on interactive input.
3. Design and build software, even operating systems, to be tried early, ideally within weeks. Don’t hesitate to throw away the clumsy parts and rebuild them.
4. Use tools in preference to unskilled help to lighten a programming task, even if you have to detour to build the tools and expect to throw some of them out after you’ve finished using them.

## Shell
On a headless server (without a graphical interface), the most popular way to interact with a server is through a terminal interface. The most widespread is a shell known as `Bash`, the Borne Again Shell.

A shell is a program that interprets user input. Emulating the look and feel of an old mainframe terminal interface, many shells like `Bash` provide their users access to several command-line interface (CLI) tools as well as useful conveniences such as auto-completion, a scripting language syntax, and I/O redirection.

To use a CLI tool a user types the name of a program followed by any parameters or flags.

## Scripting
Text files saved with the `.sh` extension are commonly used as shell scripts - a manifest of commands for Bash to run automatically line by line. To write a script, a shebang is commonly used on the first line to denote the shell program of choice. To execute a script, either pass the file as an argument to the `sh` or `bash` command, or make the file executable using `chmod` and call the file in the shell.

## GNU Core Utilities
The `coreutils` are a collection of standard Unix tools available on most Linux distributions. They include utility programs for a variety of tasks on the command line. A few examples include:
- `echo`: print a line of text
- `cd`: change directory
- `mkdir`: make directories
- `rm`: remove files or directories
- `cp`: copy files and directories
- `mv`: move (rename) files
- `ls`: list directory contents
- `cat`: concatenate and write files
- `echo`: print output of another command to stdout
- `chmod`: change access permissions
- `chown`: change file ownership and group
- `df`: shows disk free space on file systems

## Resources
### Books
- [Debian Reference](https://www.debian.org/doc/manuals/debian-reference/)
- [Conquering the Command Line](http://conqueringthecommandline.com/book/basics)
- [Linux-Training](http://linux-training.be/index.php?nav=home)
- [TLDP Advanced Bash-Scripting Guide](http://tldp.org/LDP/abs/html/abs-guide.html)

## Documentation
- [The Linux Documentation Project](https://www.tldp.org/)
- [Linux man-pages](https://www.kernel.org/doc/man-pages/)
- [Bash Manual](https://www.gnu.org/software/bash/manual/)
- [GNU Coreutils Manual](https://www.gnu.org/software/coreutils/manual/coreutils.html)
- [The Linux kernel user's and administrator's guide](https://www.kernel.org/doc/html/latest/admin-guide/index.html#)

### Tutorials
- [Linux Journey](https://linuxjourney.com/)
- [Commandline Challenge](https://cmdchallenge.com/)
- [cheat.sh - cli cheatsheets](http://cheat.sh/)
- [explainshell](https://explainshell.com/)
- [ShellCheck](https://www.shellcheck.net/)
