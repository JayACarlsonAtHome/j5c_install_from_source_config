# j5c_install_from_source_config
These files used to be in the project j5c_install_from_source_001.  
But I decided to move them to there own repository so that I can have them versioned seperately.

The install from source project (like it sounds) installs different programs from source code from various web sites.
Here is the over-view of why these projects exist:

Suppose you have a LAMP (Linux, Apache, MariaDB, and PHP) [note: mysql replaced by mariadb] system.  
You have a working system in production using CentOS 6.2, Apache 2.2.10, MariaDB 10.0, and PHP 7.0.
Now PHP comes out with some updates but you don't want to test it out on your production system.

Suppose for example your company name is zzz.
You have your production system with a setup like /.../zzz/p008/... 
the last ... represents all the LAMP programs and versions.
You use my program (on your seperate dev machine)
to create a new LAMP setup like                   /.../zzz/p009/... 
With the new version of the LAMP system you make what ever changes you need to make the website work with the new versions.
Now you can test out your changes without affecting your production server.

After your dev testing is complete you can move the code to your test machine, and let some other person test your code.
When your testing is all complete you can move the code to the production machine.  As your moving from the dev machine to the test machine,
you also create a script to automate the move to test, creating a few parameters that can be changed to substitute prod for test, for the later move.

After your testing is complete, and your move testing is complete,
You can copy the code to your production server, and repoint everything to the new directory structure.

Ok so thats the theory of this project.  So why the separate project for the config file?
Ok here is where it gets a little more complicated.  PHP and OpenSSL get updated by different teams at different times.
The newest version of OpenSSL may not work with the newest version of PHP.  XDebug may not work with the highest version of PHP either.
So this separate project is to store the configuration file where all the items work together.  Also there are other dependencies as well 
like Libzip requires cmake that is higher in version that comes from the yum based package manager. (At least when I wrote this).
Libzip is used in a lot of things like Apache, MariaDB, and PHP, and probably some more that I am not aware of at this moment.

Previously, I was just keeping the latest version of a working configuration file, but it seems to me that other people 
may just want to use the ones that I save, so they don't have to take the time to find out all the ways to make things work.
So I will tag the files with version numbers starting with 0001.
You would be surprised at how fast some of these teams are pumping out updates to their
code bases.

Notes:  For j5c_install_from_source_001 to work,
1. You need to put the executable in the same directory as the configuration file. 
2. The configuration file name must be Install_Settings.cfg
3. You must run it (Install.sh or whatever you name it.)  as root. (Install.sh needs execute permissions.)
4. Number 3 might scare you a little so run it on a machine that has no information that can be compromised on it.
5. After you run it, and are sure that machine has been secured properly, then you can move the results to another machine as you see fit, or never.










