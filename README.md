# The Shell

## Learning goals

- Learn what the shell is and start becoming familiarized with it
- Understand why server operating systems don't have a graphical user interface
- Learn what commands and arguments are, as well as how to navigate the *Linux* filesystem using the shell

## Introduction

Now that we're logged in to our Ubuntu Server instance, you might be wondering: where are all the graphics and icons?

The **shell** is a command-line interface (CLI) for interacting with the operating system. You are probably used to a graphical user interface (GUI), where you can click on icons and buttons to launch programs and perform tasks. The shell is different in that it allows you to *enter commands as text* in order to perform those same actions (and more).

While this may sound counterintuitive at first, the shell is actually a very powerful and efficient way of working with your computer. In fact, many developers opt to stay with the shell for large parts of their workflow, because in many aspects it is actually *more* efficient than using a GUI.

At its most basic level, the shell allows you to navigate your files and folders, create/delete files and directories, and run programs. But as you will find, it actually offers a vast array of features, such as the ability to *pipe* output from one command to another, using wildcards to match patterns in filenames, and writing your own shell scripts to automate both simple and complex tasks.

## Logging in

First thing's first, we need to login to our system to begin using it. After launching your VM and waiting for the startup, you should be met with a login prompt. Simply hit enter, then type your password (will not see it being typed), and hit enter again.

You should be met with the standard user prompt:

```bash
name@name:~$
```

Let's break it down:

- `name`: This should be whatever you called your user; simply refers to the current user authenticated in the shell.
- `@name`: The `@` symbol is used here to separate a user's name from their host name. In our case they are both the same so they read the same.
- `~`: This lists our current directory. The *tilde* (~) is shorthand for our user's home directory, which in reality is located at `/home/name/`.

For the sake of brevity, we will be simplifying the code examples to not show the `name@name:~$` and instead just the `$` part.

This means that when you try running the commands shown here, you should ignore the `$`; it is only there to show when something is being executed, and not something like the output of the command.

## Your first command

**Commands** are *programs* that you can run to perform various tasks. For example, the `ls` command allows you to list the files and folders in a directory. `ls` (and most commands that come preinstalled on your computer) is a program (short for *list*) stored in the `/bin/` folder.

Go ahead and type `ls`, and then hit `enter`.

If you ran it correctly, you will notice nothing got output. We just went right back to another prompt. This is because out of the box our Ubuntu Server installation does not populate our `/home/<user>` folder with anything. So let's go ahead and make a folder!

We can use the `mkdir` (make directory) command to create a directory. Run `mkdir documents` to create a folder titled `documents` in the *current directory the prompt is in*, in our case, `/home/<user>/`, or `~`. 

Now, if we try `ls` again, we should see our `documents` folder!

```bash
$ mkdir documents
$ ls
documents
```

## Directory structure

Now would be a good time to go over the directory basics when navigating in the shell.

When in the shell, you can navigate between directories using the `cd` command. To move to a subdirectory within the current directory, you can use a *relative path*, which specifies the location of the directory *relative to the current directory*.

For instance, if you are in the `/home/` (or `~`) folder, and wish to move to the `/home/documents/` folder, you can simply use the following command:

```bash
$ cd documents
```

You can also use relative paths to move to a directory that is higher up in the structure. For example, to move to the parent directory of the current directory, you can use the `..` notation. So if you would like to move from `/home/documents/` to `/home/`, you could simply use:

```bash
$ cd ..
```

Additionally, you can chain the `..` with folder names, like `../documents`, or `../../bin`.

Lastly, you will sometimes see the `.` notation to refer to the current directory. So like in the first example, if you would like to move to the `/home/documents/` folder from the `/home/` folder, you could also execute:

```bash
$ cd ./documents
```

## Arguments

Commands can be followed most of the time by one or more **arguments**, which are additional pieces of information that modify the behavior of the command. For example, our `ls` command can be followed by the `-i` argument, which causes it to show the inode number of each file in the directory, instead of just the names. 

To find out what arguments are available, or generally, how to use a certain command, you can use the `man` command.  In order to use `man`, simply run `man <command>`, replacing `<command>` with the command you want to learn how to use. 

Running `man ls` will give you a lengthy description of how the command works and what all the arguments do. To navigate through the manual page, you can use the `up` and `down` arrow keys to move through the text, and `spacebar` to move forward by one page at a time. To exit the manual page, you can press the `q` key.

## Conclusion

Follow on to the next chapter to learn more essential *Linux* commands/programs, part of what is known as the **GNU Coreutils**. 
