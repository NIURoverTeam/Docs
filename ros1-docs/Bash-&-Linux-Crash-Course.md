## Quick Introduction

**Bash** is a special type of program called a _shell_ that allows you to interact directly with your computer's operating system. Generally speaking, you interact with shell programs by typing _commands_ into a text-based interface called a _terminal_ (also known as a _command line_). Bash and other shell programs like it are closely related to UNIX, a family of operating systems that includes Linux. On the NIU Mars Rover team, we often use Ubuntu as our preferred UNIX-like operating system (something you'll likely have already installed from [this guide](https://github.com/NIURoverTeam/RoverCoreOS/wiki/Running-ROS-on-Windows#install-the-wsl-and-bash-on-windows)), which uses Bash as its shell.

UNIX-like operating systems were first created all the way back in the 1970s, and today they form the backbone of almost all modern computers and computer systems. By learning how to use and interact with Bash and other UNIX-like systems, you'll discover a secret world of technology that allows you to gain an amazing level of control and freedom over computers and how they work. This crash course will hopefully get you up to speed on some of the basic concepts of how to use Bash.

## Commands: how are they structured?

In Bash, the majority of your actions will be in the form of commands. Commands use the following structure (things in [brackets] are optional and will depend on the command being used):

`$ command [-options] [arguments]`

Let's break down each part of that.

* First is the `$`. This is shorthand for what's known as the _command prompt_. You won't actually type this at the terminal - the main point of it being in guides is to let you know that the following text is a shell command. You might also see this as `%` in guides, which means the same thing. In Ubuntu, the command prompt will likely look something like `username@hostname:~$`, or similar.
* Next is `command`. This is the command you want the shell to run. For example, `echo` is a command that repeats back what you give as arguments. Open Ubuntu from the start menu (if you don't have it, install it using [this guide](https://github.com/NIURoverTeam/RoverCoreOS/wiki/Running-ROS-on-Windows#install-the-wsl-and-bash-on-windows)), and type `$ echo This is a test` and then hit Enter (note: don't include the `$` when you type it! It's just included here to let you know the following text is a shell command). `echo` is the command in this case, and it prints its output to the terminal when it's done running.
  * If you see something like `$: command not found`, that means you typed the `$` and Bash thought that was the command you wanted to run instead of echo. Type the line again without the dollar sign and it should work.
* The next part is `[-options]`. In UNIX-like systems, command options are specified using a hyphen, and are usually a single letter. For example, a possible option for echo is `-n`, which suppresses the **n**ewline after the output. Try typing `$ echo -n This is a test` and see how it differs from the last example. A command can accept anywhere from no options to many options.
* The last part is `[arguments]`. Some commands accept arguments, which will alter their behavior. In the previous example, we were giving the echo command 4 arguments: `This`, `is`, `a`, and `test`. Bash generally separates arguments based on spaces, so each separate word we gave `echo` was a separate argument. A command can accept anywhere from no arguments to many arguments.

## The UNIX File System

All UNIX-like operating systems share a similar file system structure. The entire file system is made up of two things: _directories_ (similar to folders in Windows and Mac OS), and _files_. All files and directories on the machine are inside the topmost directory called the _root directory_, which is represented as `/`. There's also the _home directory_, which is where most of your files will be. The home directory is represented as `~`. When inside a terminal, the _working directory_ or _current directory_&mdash;the directory you're currently in&mdash;is represented as `.` (one period). The _parent directory_&mdash;the directory one level above your working directory&mdash;is represented as `..` (two periods). There are two ways to express paths to a file: either an _absolute path_ which references a file's location from root (e.g. `/home/username/mydir/file.txt`), or a _relative path_ which references a file's location from your working directory (e.g. `mydir/file.txt`). Absolute paths start with `/`, whereas relative paths do not.

That might sound like a lot, but it's fairly simple once you start using it. The next section on commands will provide some useful commands that will allow you to start learning how the file system works by actually exploring it. One of the best ways to learn is through experience, after all. So, without further ado...

## Common Commands

The following commands are some frequently used ones that will serve you well as you start using Bash. They are a small snippet of the many commands out there, but this list will be a good starting point from which to build your knowledge. It's recommended that you **open Ubuntu from the start menu** and follow along. 

* `pwd`
  * `pwd` is the first command we'll discuss. The way to remember it is that it's short for "print working directory." What this does is provides the absolute path to your current working directory. This is helpful for figuring out where you are in your file system. Run `$ pwd` in the Ubuntu terminal you opened (don't type the dollar sign!), hit Enter, and see what it says. It'll likely be something along the lines of `/home/username`, with "username" being something specific to your computer. This is the absolute path to the directory you're currently in.
* `mkdir`
  * `mkdir`, short for "make directory," does what the name implies: it makes a new directory. When you run `$ mkdir new_directory` and give it a directory name in place of "new_directory", it will create a directory with that name. For example, run `$ mkdir test_dir`. It won't produce any output, but it will have created a new directory named `test_dir` in your current directory.
* `ls` 
  * `ls` is a very useful command, short for **l**i**s**t. What it does is lists all files in the current directory. If you run `$ ls`, you will see `test_dir`, and potentially some other files and/or directories. `ls` is listing all the directories and files inside our current directory, including `test_dir`, the directory we just made. 
    * If we add the options `-l` for "use **l**ong format" and `-a` for "**a**ll files, including hidden ones", our output will look different: run `$ ls -l -a` and you'll see that more information is shown about each files, and that `.` and `..` are now listed, which were previously hidden. These are paths to the current directory `.` and the parent directory `..`, which are always present. `ls -l -a` can also be typed as `ls -a -l`, `ls -la`, or `ls -al` and it'll work the same. This structure is how all options for commands work.
* `cd`
  * `cd` is short for "change directory." What it does it moves you around the UNIX file system by changing your working directory. To understand this, run `$ pwd`. You'll likely see something along the lines of `/home/username`. Now run `$ cd test_dir` to change your working directory to `test_dir` by supplying the command with a relative path. When you run `$ pwd`, you'll see that your working directory is now `/home/username/test_dir` instead. If you run `$ cd ..` to go to the current parent directory (i.e. the directory one "above" this one) and then `$ pwd`, you'll see that you're back where you started. With this simple command, you'll be able to traverse all of your computer's file system.
    * If you run just `$ cd` and don't provide an argument to it, it will automatically take you to your home directory. This is the same as running `$ cd ~`.
* `nano`
  * `nano` is a text editor program. There are other ones such as `vim` or `emacs`, but `nano` is the most beginner-friendly so it's likely the one you'll start on. If you supply an existing file as the command argument then nano will open it to edit it, or if the file doesn't exist then nano will create it and allow you to start editing. Run `$ nano test_file.txt`, write some message in the file, hit Ctrl-O and Enter to "write **o**ut" the file (meaning save it), and then Ctrl-X to exit nano. If you run `$ ls`, you'll see that there's a new file called `test_file.txt` that we just created. If you run `$ nano test_file.txt` again, it'll open the existing file and let you edit it further. 
    * Note: clicking doesn't do anything in nano! You have to use the arrow keys to navigate. Ctrl-O and Enter to write out (AKA save) the changes when you're done, and Ctrl-X to exit nano.
* `cp`
  * `cp` is short for **c**o**p**y. The format is `$ cp source destination`. For example, let's say we wanted to copy our test_file.txt into test_dir. To do so, we would run `$ cp test_file.txt test_dir`. If we cd into test_dir, we will see that there's now a duplicate of our file, and viewing it in nano will show that the contents is the same too. 
    * If `destination` is a directory, `cp` will use the same name as the source file. If `destination` is a file (e.g. `test_dir/test_file_copy.txt`), then that new name will be used but the contents will be the same.
* `mv`
  * `mv` is short for **m**o**v**e. This command moves files from one location to another, using the format `$ mv file_to_move new_file_location`. `mv` is also how you rename files in UNIX: by running e.g. `$ mv old_name new_name`, you'll rename the file.
* `rmdir` 
  * `rmdir` is short for "remove directory." This command only removes empty directories, so you can use it without fear of accidentally deleting directories with important contents in them. The format is `$ rmdir dir_to_remove`.
* `rm`
  * `rm` is short for **r**e**m**ove. This command is similar to `rmdir`, except this one can remove regular files too. It can also be used to remove non-empty directories and their contents by running `$ rm -r directory_to_remove`, with the `-r` option meaning "remove **r**ecursively." **WARNING: THERE IS NO UNDO OPTION OR TRASH BIN FOR `rm`!!! _FILES ARE IMMEDIATELY GONE AND UNRECOVERABLE._** Use carefully&mdash;you have been warned.
* `man`
  * The last command we'll discuss is `man`, which is short for "manual." Using this command plus another command as the argument (e.g. `$ man ls`) will provide the "manual pages" for the requested command, which is like its official documentation. They're a little technical, but as you start learning more commands the man pages can be very helpful sources of information. 
    * `$ man man` provides the manual page for the concept of manual pages itself, as well as a table of contents.

There are many other commands out there (and eventually you can even make your own commands!), but this list is a good starting point and is sufficient to get a lot done as it is. 

As a final tip, you can auto-complete in the terminal by hitting Tab. For example, let's say you wanted to copy the `test_dir` directory from earlier using cp. To do so, you could type `cp t` and then hit Tab. It will auto-complete as far as it can; if you still have `test_file.txt` from earlier, it will auto-complete up to `cp test_`. If you now hit Tab twice in a row, it will list all completion options (in this case that might look like `test_dir/      test_file.txt`). You can type the beginning of the option you want (e.g. `cp test_d`) and then hit Tab, and it will auto-complete it to `cp test_dir/`. Using this technique can greatly increase your speed once you get the hang of it, but it's not necessary.

***

Once you're done exploring Bash concepts here, consider checking out our [Git & Github Crash Course](https://github.com/NIURoverTeam/RoverCoreOS/wiki/Git-&-GitHub-Crash-Course).