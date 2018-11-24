
# Arch install script

The inst script is my Arch install script written in bash. It installs Arch base + base-devel with an xfce DE. It's designed primairly as a template needing edited before use. 
I'd like to think of it as somewhat of a balance between being minimal but also thorough enough to be a reasonable time saver, while making things easy for the user. <br>

Tested in vbox and a work in process.<br>
Note: I need to step things up with updating/replacing my preferred msdos partition table. As far as I know, there's not been new hardware 
available that's compatible with this for quite some time.

To run the inst script from the official Arch install iso:

Download the latest Arch iso : https://www.archlinux.org/download/ <br>
I'll leave getting it going to you.

From the Arch install iso run:

Fetch the script: <br>
 wget https://raw.githubusercontent.com/Cody-Learner/inst/master/inst <br>
 chmod +x inst

Or optionally, use tinyurl: <br>
 wget https://tinyurl.com/cody-inst <br> 
 mv cody-inst inst <br> 
 chmod +x inst

Verify file integrity: <br>
 $ md5sum inst
1a142b095ab160df69f5040f0ea216fa  inst

To start the script run: <br>
 ./inst

<br>
<br>
<br>
<br>
<br>
<br>

2018-11-23 [SOLVED] (logging below)          

Went with vipe of the moreutils package, combined with command grouping across functions, pipe with stderr, ( ie: |& ) and tee. 
However, using vipe was not without issues. It initially required a bunch of manual typing in nano to correct file paths, when implenented within a simple set of pipes. 
Eventually figured out a workaround (more complex than originally, see script) that allows normal nano viewing, editing, and saving conf files without requiring a bunch of extra, error prone steps.
Also made a first effort at expermenting with error detection, if it actually falls within that category. Just setting a variable (number 1) to each function if it finishes running.
Then add vars up in the end, and use the sum in a cleanup function called with trap. Enjoyed implementing it, although obviously not as useful at helping with error trouble shooting as it is at 
cleaning stuff up if a function fails or crashes.





2018-11-19 EDIT: Logging is currently a wip, has changed, and is not yet feature stable.<br>

Testing:
 * Tried all the std redirection, pipe + tee, w and w/o process substitution combos. Screws up nano usage in script when redirecting stderr, ie 2>&1 or |&. <br>
   (I've since learned using an interactive editor in a script is considered "poorly designed", but too tenacious to give up just yet.) <br>
 * 'script' program. Too many lines output, ie: too large for remote log saving.
 * named pipes (fifo's) and redirection <br>
 * 'logsave' program using 'more' as the log reader <br>
 * asciinema terminal recorder and player <br>
<br>
<br>
Screenshot inst.log: https://cody-learner.github.io/logsave.html
