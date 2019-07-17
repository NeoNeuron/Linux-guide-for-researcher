# Computing Server Short Manual for Researcher

>(Updated until : 2019-07-16)

>Author : xyy, kchen

>		Write programs that do one thing and do it well.
>		Write programs to work together.
>		Write programs to handle text streams, because that is a universal interface.
>                                             ---- Unix philosophy (Peter H. Salus)


Backgrounds and Concepts
========================

Unix
----
Unix is an operating system that originally developmented at the Bell Labs, by Ken Thompson, Dennis Ritchie, and others in 1970s. Ken Thompson invented the B programming language, the direct predecessor to the C programming language, Dennis Ritchie created the C programming language.
Unix's genius design and continuing improvements make it popular and long lasting till today. What's more important, had significant impact on other operating systems (including Mac and Windows).

Long Live Unix!

[1] [UNIX演义](https://bbs.sjtu.edu.cn/bbs0an,path,%2Fgroups%2FGROUP%5F3%2FUnix%2FD915C16C6%2FDA27A696E.html)


Linux
-----
Linux is a spiritual successor to the original Unix system. Both of them (and also macOS) are mostly POSIX-compliant [2]. POSIX [1] is a standard that maintain software compatibility between variants of Unix and other operating systems. For example, C source code should be (almost) interchange between (almost) POSIX-compliant systems.
When we say the system is Unix-like, we usually mean the system is mostly POSIX-compliant.

POSIX standard covers general concepts, system interfaces, shell & utilities etc. It is unlikely that you will need to read it as a beginner or even as an experienced user.

* [1] [POSIX.1-2017. The Open Group Base Specifications Issue 7, 2018 edition.](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/)
* [2] [POSIX, Wikipedia](https://en.wikipedia.org/wiki/POSIX)


GNU and Free Software
---------------------
GNU means GNU's Not Unix. ;-)

It is the name of a software project lead by Richard Stallman (RMS). The GNU project aims to create a free operating system and a free software toolchain on top of it, by collaboratively developers.

Free here means: the users are free to run the software, share it (copy and distribute), study it, and modify it.

In order to (legally) guarantee these freedom, a licence is necessary: The GNU General Public License (GNU GPL or GPL), which is a "copyleft" licence, in contrast to "copyright". In simple words, it means that you must publish your source code and licence it under GPL, if it is a derivative work from a GPL licenced code and you are distributing or selling it (with or without charge). See [2,3] for details.

Examples of Software in GNU projects:

  GNU Compiler Collection (GCC), GNU C library (glibc), GNU Bash shell, GNU Core Utilities (i.e. basic Linux commands), GNOME desktop environment, GNU Octave, GNU Emacs, GIMP ("photoshop" for Linux), Gnumeric (MS Excel compatible).

Example of GPL or LGPL licenced or GPL/LGPL compatible softwares:

  Linux, Firefox, Python, Android (the core part), TensorFlow, 7z, LyX, pdfTeX.

Example of NON GPL/LGPL compatible softwares

* Intel Math Kernel Library, i.e. MKL (Freeware, but not opensource, not free to share).
* Matlab
* macOS
* QQ, WeChat, Skype
* MS Word, MS Excel, Visual Studio, etc.

Ref.

* [1] [The GNU Project, by Richard Stallman](https://www.gnu.org/gnu/thegnuproject.en.html).
* [2] [GNU General Public License](https://en.wikipedia.org/wiki/GNU_General_Public_License).
* [3] [GNU Lesser General Public License](https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License).


Linux Distributions (发行版)
---------------------------
Linux kernel together with a large set of user softwares (in a place called software repository). e.g. Ubuntu, Debian, Fedora.

In most cases, you will use a "Linux distributions" instead of assembling a Linux kernal and user softwares yourself.

Some Linux distributions focus on out-of-the-box (Ubuntu), some focus on bleeding edge software (Arch, Fedora), some focus on stability (Debian, CentOS).


Software Repository
-------------------
Also called software source.

Software repository is a website that stores and publishes a collection of free softwares that specifically tuned for the distribution. The repository is maintained by developers of the distribution and possibly the original author of the individual software. The softwares in the repository could come from everywhere, e.g. GNU projects, amateur projects, academic projects, commercial projects.

The software repository could also contain non-free softwares, non-free in the sense that they are not GPL or LGPL compatible. e.g. mp3 decoding and encoding technology (patented, but expired 2017), nvidia-driver (not open source).


Why Choose Linux
================

* No annoying advertisement, more safe

  Mostly, you will install softwares from the software repository. Softwares from official repository are verified and will be securely downloaded, thus avoid the risk of malicious softwares, and with no ads. High priority security fix will be patched in a urgent pace (within few days after been found).

* Let *you* control your computer

  No unawared background programs running e.g. automatic software updata, force system reboot, virus scan, unexplained internet traffic or CPU usage etc.
  
  No hiding/joking of CPU usage, network traffic, RAM usage etc.
  
  Source code are available, when in doubt, or want to make some improvement, or want to learn from it, just check its source code (apt-get source _packagename_).

* Run faster

  Linux has a better CPU scheduler and RAM memory management compared to Windows in general. Thus programs could run a few percent (sometimes more than 10 percent) faster after transplant to Linux. e.g. it is observed that Linux version of Mathematica is faster than its Windows version, likely Matlab behaves the same.

* Rich set of tools for advanced user
    - For administration of system
    
        See hardware details without installing extra softwares.
        
        Highly configurable and with fair documentation (man).
        
    - Good for batch processing
    
        Easy to automate complex procedures.
        
    - For programming
    
        Pre-installed gcc and python. Nice editors (vim, gedit). Powerful debug/profiling tools.

* A lot of research-oriented programs are developed under Linux, or best running under Linux. For example

   - LaTeX (run faster, much easier to install)
   - NEST Simulator (Linux only?)
   - NEURON (Linux only)
   - GNU Octave (much faster)
   - FFTW, LAPACK (much easier to compile)
   - TensorFlow (much easier to compile)
   - ssh (you can have Graphical user interface, without using vnc)

* 100% of world top 500 super computers are running Linux.

  At Jun. 2004, for the first time, more than 50% of super computers are running Linux. Then soon Linux dominate super computer list (85% at 2007), eventually reaches 100% at Nov. 2017 and remains today.

[1] [Top 500 / Statistics / Development over Time](https://www.top500.org/statistics/overtime/)


Where to Start and How to Learn Linux
=====================================

[鸟哥的linux私房菜](http://linux.vbird.org/). Although reads verbose, it sometime quite beginner-friendly.

To really learn Linux, you should force yourself to use it for all your works. So start by pick up a Linux distributions. e.g.

  * Debian   http://www.debian.org/
  * Ubuntu   https://www.ubuntu.com/
  * Fedora   https://getfedora.org/

They all come with good documentations. Just follow the documentation to start your journey.

Linux might not have the exactly same software as in Windows or Mac, but there are softwares to achieve the same purpose.

Record useful commands/softwares in your personal notebook.

  There are few tasks that are impossible or too costly to be done under Linux. You might need a virtual machine or Wine [1].

    1. Login bank of China.
    2. QQ, wechat. (alternatives: use web based wechat, http://wx.qq.com/)
    3. Games. (alternatives: Use Wine, or dual boot with a real Windows)

[1] WineHQ - Run Windows applications on Linux, BSD, Solaris and macOS. https://www.winehq.org/


Where to Get Help
=================

> RTFM (Read The Fucking Manual)
>               ---- a word you might heard when asking for help.

* Search in Google, with keywords and name of your Linux distributions

* Most commands come with a manual

  You can open a command window and type `man` _commandname_ to access its documentation. Or type `man man` to get help of `man` itself.


File System Organization
========================

> "Everything is a file"
>            --- a feature of Unix(-like) system

Linux (absolute) path starts by a slash "/", called root directory, there is *no* `C:\` or `D:\`.

The separator between directories is "/", in contrast to Windows' "\\".

Relative path starts by ".". e.g.

  - `./a.txt`, file `a.txt` in the current directory.
  - `../a.txt`, file `a.txt` in the directory of one level up.
  - `../b/a.txt`, file `a.txt` in the directory of one level up then down into `b`.

"~" is short for your home directory "/home/${USER}", "${USER}" is your user name.

Unlike Windows, Linux directories are arranged by their category (e.g. program, setting, library or document), not by software name or company name.

	/home       user data all go here
	/boot       linux kernal and configurations about booting.
	/bin        essential system programs (commands)
	/lib        system library
	/etc        system configurations. mostly in plain text.
	/usr/bin    general software executable
	/usr/lib    general software library
	/usr/share  software documentation and (default) settings
	/var/log    system logs
	/dev        hardware devices (shown as files)
	/proc       information about currently running programs
	/sys        settings of hardware and linux kernel


The files of a software will be spread in /usr/bin, /usr/lib, /usr/include, /usr/share etc., according to the catalog of each file. Unlike Windows software, mostly in C:\Program Files. In order to manage the spreading files (and software dependency), most Linux systems come with a "Package Manager". In Debian (also Ubuntu), it is APT (command `apt-get`).

Every file has access permission, can be shown by command `ls -l`, can be modified by command `chmod`.

"root" user has the absolute right to do every thing, including deleting the system itself.

To see the full path to the command, use command `which`. e.g. `which python`.


One Day in Linux
================
Assume Bill is going to work on our computing server(bill@zcpu), and your local machine is also running Linux (or Unix-like), (bill@laptop).

###Login

```bash
$ ssh -p 68 bill@202.121.1.119
```

Bill wants to run a test C program. So he opens a text editor

```shell
$ nano
```
```c++
#include <stdio.h>
int main() {
	printf("Hello?\n");
  return 0;
}
```
```nano
C^X
```
name it abc.c

Now to compile it
```shell
$ gcc abc.c -o abc
```

And run it
```shell
$ ./abc
```
Hello?

OK, works.

Now Bill wants to upload his own files to the server.

```shell
$ scp -v -P xx /home/bill/work bill@xxx.xxx.xxx.xxx:/home/bill/
```

Now Bill finds that constantly typing the address and port is anoiying. So let's alias it

```shell
$ nano ~/.ssh/config
```
add following lines into ssh config file
```vim
Host zcpu
	HostName xxx.xxx.xxx.xxx
	Port xx
	User bill
```

Now Bill can use upload files in a much simpler way.

```shell
$ scp /home/bill/work zcpu:/home/bill/
```

Similarly for download data from the server.

```shell
$ scp zcpu:/home/bill/data /home/bill/
```

Now Bill can login in like this.

```shell
$ ssh zcpu
```

### Operation of Files

After uploading his own file, Bill wants to create a new folder to store his files.

```shell
$ mkdir foo
```

Now move files to the new folder.

```shell
$ mv ./work ./foo/
```

Then move to the new folder and rename work.

```shell
$ cd foo
$ mv work raw_file
```

Now Bill wants to create a copy for raw_file.

```shell
$ cp raw_file new_file
```

Besides, Bill wants to know the information of files in current folder.

```shell
$ ls -l 
total 16
-rw-r--r--  1 bill  bill  1 Jul  7 12:02 new_file
-rw-r--r--  1 bill  bill  1 Jul  7 12:02 raw_file
```

Now Bill wants to delete new_file.

```shell
$ rm new_file
```

### Operation of File Content

Bill wants to edit the content of raw_file. So he uses nano to open rawfile.

```shell
$ nano raw_file
```

Bill wants to save his new changes in raw_file and exit nano.

```nano
C^X
```

#### Tips for `nano` usage
Nano is a user-friendly text editor for terminal users. Just treat it as the usual text editor in Windows or Linux GUI, though without mouse operation support. Most commonly used shortcuts are listed on the statue bar at the bottom of the window. You can easily get detailed documantations with `Ctrl`+`h`.

### Inspecting system

When using the computating server, Bill wants to inspect the state of operating system as well as programs and the available resources.

First of all, about the current size of home directory.

```shell
$ du -sh $HOME
```

Total usage of file system and available disk space.

```shell
$ df -ht ext4
```

Specifications of the server's CPU

```shell
$ lscpu
```

Information and current state about server's GPU (only available on GPU server)

```shell
$ nvidia-smi
```

Most importantly, Bill wants to inspect his programs as well as the resource available on the server.

`$ top`

	top - 23:27:57 up 25 days,  6:30, 15 users,  load average: 18.23, 15.50, 8.92
	Tasks: 826 total,   2 running, 518 sleeping,   0 stopped,   0 zombie
	%Cpu(s): 25.6 us,  6.8 sy,  0.0 ni, 67.6 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
	KiB Mem : 26358241+total,  1502220 free, 18863252+used, 73447664 buff/cache
	KiB Swap:        0 total,        0 free,        0 used. 73098776 avail Mem

	  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND
	19899 mike      20   0 9640456 1.072g 248604 S  2002  0.4 186:07.75 MATLAB
	19272 john      20   0  0.171t 0.171t   3340 R  99.7 69.6  72:10.56 t3
	20426 mike      20   0   49704   4872   3436 S   1.6  0.0   0:08.43 top
	19555 john      20   0   49732   4996   3484 S   1.3  0.0   0:36.48 top
	21401 bill      20   0   49740   4816   3448 R   1.3  0.0   0:00.50 top
	55645 mike      20   0   49836   5176   3500 S   1.3  0.0  56:45.55 top
	    9 root      20   0       0      0      0 I   0.3  0.0  14:03.25 rcu_sched
	 4708 gdm       20   0  591400  27924  17284 S   0.3  0.0  31:56.19 gsd-color
	 4828 kernoops  20   0   56936   2364   1912 S   0.3  0.0   0:56.01 kerneloops
	    1 root      20   0  226096   9896   6668 S   0.0  0.0   0:33.61 systemd
	    2 root      20   0       0      0      0 S   0.0  0.0   0:00.32 kthreadd
	    4 root       0 -20       0      0      0 I   0.0  0.0   0:00.00 kworker/0:0H
	    5 root      20   0       0      0      0 I   0.0  0.0   1:30.69 kworker/u128:0
	    7 root       0 -20       0      0      0 I   0.0  0.0   0:00.00 mm_percpu_wq
	    8 root      20   0       0      0      0 S   0.0  0.0   0:01.32 ksoftirqd/0


The first two lines illustrate the total up time, the number of users, the number of tasks, the number of running tasks of the server. The third line shows the detailed CPU usage, with `us` for user usage, `sy` for system usage, `wa` for waiting usage. (**NOTE**: if `wa` percent is high, which CPU is waiting for I/O operations, it might indicate the I/O bottle neck of your program.) Next two lines shows the detailed RAM(memory) and swap usage.

The rest of table lists all the detailed information about all processes. By default, they are sorted in the descent order of CPU usage. Pay attention of the `RES` column, which is the actual memory usage of processes.

#### Tips for top
- press `e` to change units of each process (None->k->m->g->t->p: B->KB->MB->GB->TB->PB)
- press `E` to change units of total resources (None->k->m->g->t->p: B->KB->MB->GB->TB->PB)
- press `k` and the PID of target process to kill the target process

	e.g. to kill the bill's top process, whose PID is 21401

	```shell
	$ k
	$ 21401
	$
	```

    It is possible that the program refuse to exit (e.g. MATLAB), in which case you can send the program a "signal 9".

	```shell
	$ k
	$ 21401
	$ 9
	```

- use `>` and `<` to change the sort column of processes (default sort column is %CPU)

`$ ps aux|grep |less`

Bill opened 10 python processes by accident. So he wants to kill all of them together.

```shell
$ jobs
[1]    suspended (tty output)  python
[2]    suspended (tty output)  python
[3]    suspended (tty output)  python
[4]    suspended (tty output)  python
[5]    suspended (tty output)  python
[6]    suspended (tty output)  python
[7]    suspended (tty output)  python
[8]    suspended (tty output)  python
[9]  - suspended (tty output)  python
[10]  + suspended (tty output)  python
```

```shell
$ pkill python
```

### Internet

Bill wants to download a file from http://website.com/files/file.zip over HTTP.

Firstly, he needs to check whether the internet connection is avaiable.

```shell
$ ping website.com
```

Then, Bill can simply use `wget` command to download the file.

```shell
$ wget http://website.com/files/file.zip
```

### TMUX

Occasionally, Bill would suffer from the broken pipe issue. In case of losting working data, Bill decides to use tmux on server.

Start a new session
```shell
$ tmux
$ tmux new
```

Detach from session
```shell
$ Ctrl-a  d
```
i.e. press the key Ctrl and the key A simultaneously, release both, then press the key D.

List existing sessions
```shell
$ tmux ls
```

Attach to last session
```shell
$ tmux attach 
```

Exit and close current session
```shell
$ exit
```

Create new window
```shell
$ Ctrl-a  c
```

Close current window
```shell
$ Ctrl-a  &
```

Next window
```shell
$ Ctrl-a  n
```

Switch/select window by number
```shell
$ Ctrl-a  0 ... 9
```

More instructions : https://tmuxcheatsheet.com

### History operations

Bill suddenly forgets to the gcc command to compile c++ code. So he goes to history command to look up his previous command.
```shell
$ history
```

However, there are too much commands' histories to be contained in a single screen. So Bill uses history command together with less command in a pipe line format.

```shell
$ history | less
```

Now Bill can just use up and down button to browse all history contents one by one. Besides, to find the gcc command, simply, Bill uses the keywords searching function.

```vim
/g++
```

Tips:

* Use `n` to search the next occurrence, `Shift-n` to search the previous occurrence.
* Type `-i` to ignore (or not ignore) case in searches.


Programming tips
================

### GCC and Linking Principle

Bill writes a C++ project which contains several files, including main.cpp, functions.cpp, functions.h. Now he need to compile those header file and source files into a excutable program.
```shell
$ g++ -o exc.out functions.cpp main.cpp
```

In the compiling command above, one option is explicitly specified.

`-o` output file

There are other useful options, including

- `-l` Link on Objective-C and Objective-C++ program, e.g., `-lm` `-lfftw3`
- `-I` Add the directory dir to the list of directories to be searched for header files during preprocessing.
- `-L` Add directory dir to the list of directories to be searched for -l
- `-O`, `-O2` Compile with optimization (-Os, -O, -O2, ...)

#### Sanitizer

Sometimes, there are some potential undefined behaviors or events of memory leaking in Bill's program. Thus, in order to enable run-time analysis for those dangrous events, Bill uses the follow compiling options.

	-fsanitize=undefined
	-fsanitize=leak

#### Compile and Install External Softwares

Now Bill needs to compile and install external softwares from source files. Here is one of the commonly used procedures.
```shell
$ cd /path/of/source/				# move to the directory of source files
$ mkdir -p build				# create build directory
$ cd build					# move to build directory
$ ../configure --prefix=/path/to/install/	# config compilation with prefix option
$ make						# make target files
$ make -j 32					# or make in parallel with 32 cores
$ make install					# copy the built files to the target directory, specified with prefix options in ../configure step
```

### Profiling

Bill's program suffers a low performance. Bill analyzes its performance using perf.

First of all, program needs to be compiled with specified option '-g'.
```shell
$ g++ -o exc.out functions.cpp main.cpp -g
```

Run perf to record the performance. Use the program as usual during profiling.
```shell
$ perf record ./exc.out
```

Call perf report to view the performance report.
```shell
$ perf report 
```

More details : https://perf.wiki.kernel.org/index.php/Tutorial


### PATH, and Other Environmental Variables

_Environmental variables_ are named values which can be accessed by running programs. It is used as a mechanism to pass parameters to subprocess (program that is started by another program), thus affect the subprocess' behaviour. For example, Shell, as a subprocess of OS, uses `PATH` to determine where to find runnable commands. When starts a program from a Shell, all the environmental variables in that shell will be copied and passed to the program just started, the program is then allow to read and modify its own copy of environmental variables.

In most Shell (e.g. Bash), prepending a `$` sign to the variable name means substitute its value in situ, thus `
$PATH` prints the value of `PATH`.

`PATH` is an environmental variable in Linux and other Unix-like operating systems that tells the shell which directories to search for executable files (i.e., ready-to-run programs) in response to commands issued by a user.

Several ways to view the contents of PATH.
```shell
$ env | grep PATH
$ echo $PATH 
```
```shell
/opt/dell/srvadmin/bin:/opt/dell/srvadmin/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
```

Look at the contents of PATH variable, which are bunches of colon-seperated directories. Now Bill wants to add the directory /usr/sbin to the PATH.
```shell
$ export PATH=$PATH:/usr/sbin
```

Now, view the contents of PATH again.
```shell
$ echo $PATH
```
```shell
/opt/dell/srvadmin/bin:/opt/dell/srvadmin/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/usr/sbin
```

Note that, an addition to a user's PATH variable can be made permanent by adding it to that user's .bash_profile file. .bash_profile is a hidden file in each user's home directory that defines any specific environmental variables and startup programs for that user.

**Remarks:**
The same mechanism exists for other types of files that some program is going to search for by name. Here are a few typical PATH-like variables.

- `PATH`: executables (e.g. /home/username/bin:/usr/local/bin:/usr/bin:/bin).
- `MANPATH`: manual pages (e.g. /usr/local/man:/usr/man).
- `LD_LIBRARY_PATH`: native code libraries (on Linux, in addition to the value of this variable, the lookup path typically contains /usr/local/lib, /usr/lib, /lib and a few others). The name LD comes from dynamic loader, the system component that loads libraries into dynamically linked executables.
- `PYTHONPATH`: Python libraries (e.g. /usr/local/lib/python:/usr/lib/python:/usr/lib/python2.7).


Recommended Softwares 
=====================
(on your own laptop with Unix-like operating system)

Meld
----
Meld is a visual diff and merge tool targeted at developers. Meld helps you compare files, directories, and version controlled projects. It provides two- and three-way comparison of both files and directories, and has support for many popular version control systems.

Meld helps you review code changes and understand patches. It might even help you to figure out what is going on in that merge you keep avoiding.

More details : http://meldmerge.org

LyX
---
LyX is a document processor that encourages an approach to writing based on the structure of your documents and not simply their appearance.

LyX combines the power and flexibility of TeX/LaTeX with the ease of use of a graphical interface. This results in world-class support for creation of mathematical content (via a fully integrated equation editor) and structured documents like academic articles, theses, and books. In addition, staples of scientific authoring such as reference list and index creation come standard. But you can also use LyX to create a letter or a novel or a theatre play or film script. A broad array of ready, well-designed document layouts are built in.

LyX is released under a Free Software/Open Source license, runs on Linux/Unix, Windows, and Mac OS X, and is available in several languages.

More details : https://www.lyx.org/Home
