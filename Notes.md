# Set up SSH keys on CENTOS
ssh-keygen

# Add keyto Putty 
Still Not worked

# Connect CentOS using Remote IP and ssh keys
Still Not worked

# to search header files for particular definitions and function prototypes change to the /usr/include   directory and grep, grep searches all the files in the directory with a name ending in .h for the string EXIT_.
grep EXIT_ *.h

# The cat command in Linux concatenate files and displays the output to the standard output (usually, the shell)
cat anyfilename

# utilities and pipes the output of the file listing to a screen-at-a-time display
ls -al | more

# print a reference copy of the bash manual pages (lpr?)
man bash | col -b | lpr 

# check the version of bash (/bin/sh: —version: No such file or directory)
/bin/sh —version --Not working

# saves the output of the ls command into a file called lsoutput.txt
ls -l > lsoutput.txt

# will append the output of the ps(process status) command to the end of the specified file ()
ps >> lsoutput.txt

# put the output and error information into separate files (not worked out )
kill -HUP 1234 >killout.txt 2>killerr.txt

#  to combine the two outputs, will put both the output and error outputs into the same file (not worked out )
kill -1 1234 >killouterr.txt 2>&1

# UNIX universal “bit bucket” of /dev/null to efficiently discard the entire output (Not worked out)
kill -1 1234 >/dev/null 2>&1

# more command is quite happy to accept filenames as parameters (What this cmd does?)
more < killout.txt

# We can connect processes using the pipe | operator
ps > psout.txt  
sort psout.txt > pssort.out  
ps | sort > pssort.out  
ps | sort | more

# we want to see all the different process names that are running excluding shells
# takes the output of ps, sorts it into alphabetical order, extracts processes using uniq, uses grep -v sh to remove the process named sh, and finally displays it paginated on the screen. (Not worked out)
ps –xo comm | sort | uniq | grep -v sh | more

# If you have a string of commands, the output file is created or written to immediately as the set of commands is created, so never use the same filename twice in a string of commands
# you will end up with an empty file, because you will overwrite the mydata.txt file before you read it.
cat mydata.txt | sort | uniq | > mydata.txt

# examine the files that contain the string POSIX (what -1 does)
$ for file in *
> do
> if grep -l POSIX $file
> then
> more $file
> fi
> done

# will output the name of the file whose contents contained the string POSIX
more `grep -l POSIX *`
more $(grep -l POSIX *)
grep -l POSIX * | more