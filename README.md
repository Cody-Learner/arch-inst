
# Arch install script

For virtualized hardware only. <br>
Needs edited to suit requirements. <br>
Will reformat/overwrite existing drives/partitions as is. <br>

From the Arch install iso:

Fetch the script: <br>
 curl https://raw.githubusercontent.com/Cody-Learner/inst/master/inst >inst <br>

Set the execution bit:  <br>
 chmod +x inst  <br>

To run: <br>
 ./inst

<br>


2021-04-04 UPDATE <br>

Permenant WIP status <br>
Pulled this out and dusted off the cobwebs to build a few test installs. <br>
Cleaned things up a bit and removed of some testing/experimental stuff. <br>
Set up network to use systemd-networkd and systemd-resolved rather than dhcpcd. <br>
Setup custom systemd 'display.service' for fullscreen resolution console. <br>



2018-11-23 [SOLVED] (logging below)   <br>

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
