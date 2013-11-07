# Command line and Git Workshop

Here are some notes for the command line and git workshop for Goldsmiths Hack Society.

## Command Line

The command line is the way in which people interacted with computers before GUIs existed. Because there were programmers then, and the only way they could program was through the command line, they came up with some pretty cool shit (vi, emacs, etc.). It works by using an interactive prompt in a pseudolanguage called Bash (Bourne Again SHell). Note: Some of these utilities have ridiculous names, no need to get hung up about it, it just turns out that some ancient hippy programmers were/are a bit nuts. You are given a prompt that might look something like this (it varies from system to system) `rhguh:~ Hugh$`. 

1. The first string is your computer's hostname, the word that identifies it to itself and to the programs running on it. These don't have to be unique to any individual computer, but in a networked environment it's handy for them to have different names.
2. The second string, seperated from the hostname by the `:` character is the working directory. Whenever you are at a shell, that shell is in a given directory on your system. There are commands to traverse directories, which I will get to in just a minute. The `~` sign is a special symbol for your user's home directory.
3. The third string, seperated this time by a space, is the username.
4. The fourth part is a `$` sign, indicating that you have access to a standard user shell.

Note: All of this depends entirely on your system, and is totally customisable. I'm just using this example because it is the default for Mac OS X.

## File system

The file system on unix-based systems is great! It's really straightforward, and easy to navigate on the command line. For the given filesystem tree below:

/
|---- Users ---- Hugh ---- Documents
|                   |			   | ---- java
|					| ---- Downloads
|					| ---- Pictures
|
|---- Library ---- WebServer ---- Documents ---- index.html
					           			  | ---- index.js
					                      | ---- style.css
					                      | ---- cat.gif
					                      | ---- doge.djs

When your filesystem looks like that, and your prompt says `rhguh:~ Hugh$`, what directory are you in, how do you get to your web directory?

### `cd`

You use the `cd` command. It stands for 'change directory'. On some systems it's replaced with things like chdir, and other weird stuff *cough* Windows *cough*, but on most modern systems developed by sane competent people, `cd` is used. If you're familiar at all with web development, you'll be familiar with the concept of absolute and relative paths. `cd` accepts both of these kinds of paths, and has a few of it's own shortcuts

### Absolute and relative paths

When a path begins with a `/` character, it is said to be in reference to the root directory. The root directory is like a 'master folder' in your system - everything is contained within it. Usually users are in folders called `/home` or `/Users`, and programs are in places like `/bin`, `/usr/bin`, and `/Applications`. You could type out a whole, absolute path to the web documents folder (in the diagram above) like so: `/Library/WebServer/Documents`. It will go to the same place, regardless of where you are when you use it, because it is in reference to the root folder.

When there is no `/` character at the start of a path, it is 'relative' to the directory that I am currently in. If I were in my home folder (which has an absolute path of `/Users/Hugh`), and I wanted to go to to my Downloads folder, I would not have to use the full absolute path of `/Users/Hugh`, I could just use `Downloads`. Think of it as if when there's no `/` starting the path string, the system will automatically prepend the current working directory to the command.

Important particularly to relative paths are the concepts of `.` and `..` on a unixey file system. They are symbolic abstractions of the current working directory, and it's immediate parent directory. For example, if I were in `/Users/Hugh/Downloads` and I wanted to go to my home directory, I would type `cd ..`, which means "Change directory to the immediate parent directory".

Another important filesystem symbol is the `~` symbol. It represents the currently logged in user's home directory. Wherever I am on the system, `cd ~` will always get me home.

### Other useful commands

* `pwd` - in case your prompt uses some abstract symbol for where you are, and you're not sure, you can always use the `pwd` command, which prints the absolute path of the working directory.
* `open` - in Mac OS X, you can use the `open` command to open a finder window. You can supply a path to a file or a folder as the argument, and it will open in the correct place.
* `subl` - in various operating systems you can configure them to use this command to open a sublime text window. Similar to `open`, you can supply a path and it will open a specific file or directory.
* `say` - in Mac OS X, you can use the `say` command to make your OS speak to you. It's meant to be an accessibility utility, but I'd be very surprised if there isn't a `say` based twitter client yet.
* `processing-java` - You can use this command to run a Processing sketch (once you've installed it in your system from the Processing IDE). This means you'll never have to look at that shitty IDE ever again.
* `javac` - Java compiler. If you're in PAP you've used this, if you're not, you're lucky and should never have to learn java.
* `java` - Java VM. Run a compiled Java program
* `python` - Run a python program (don't worry, there's no need to compile). You can also use `python` without any arguments to enter a `read evaluate print loop`, to let you execute python as if it were a command line language.
* `cat` - Concatenate the contents of a file.
* `echo` - repeat the argument, or the contents of an environmental variable. (or a couple of other things, or something else)
* `ls` - (I should've got to this earlier) List the contents of the directory that you're in, or the directory specified in the argument. It's very important if you want to know what's going on :)
* `cp` - Copy a file from one place to another
* `mv` - Move a file from one place to another

### Summary

There's some cool shit you can do. There's actually a lot more than I've said, there's crazy things like a command line twitter application, or a music organizer, or a matrix-style visualisation... There's a load more programming languages that do cool stuff on the command line (nearly all of them I would imagine), and features for remote connection into servers (or a raspberry pi hidden somewhere in your parent's house alongside a tb harddrive that you can store stuff on).

## Git

And also git. If everyone isn't too confused by the other stuff, then I shall do a demo of git (only because I didn't get time to write notes), otherwise, we shall circle back to it another time :)
