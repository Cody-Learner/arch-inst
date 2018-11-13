
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
 wget https://raw.githubusercontent.com/Cody-Learner/saist/master/inst <br>
 chmod +x inst

Or optionally, use tinyurl: <br>
 wget https://tinyurl.com/instarch <br> 
 mv instarch inst <br> 
 chmod +x inst

Verify file integrity: <br>
 md5sum inst

Should be: b8a77c24e53722c69b6f520c4c11de6a  inst


To start the script run: <br>
 ./inst

The script will initially set up logging via an alias in the arch iso. This will take just a few seconds, then a message appears. <br>
Follow the instructions from there which are: <br>
Exit the terminal or source .zshrc. <br>
Call the script using 'inst', rather than './inst' the second time.
