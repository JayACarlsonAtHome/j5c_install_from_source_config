# j5c_install_from_source_config
These files used to be in the project j5c_install_from_source.  
But I decided to move them to there own repository so that I can have them versioned seperately.

The install from source project (like it sounds) installs different programs from source code from various web sites.
Here is the over-view of why these projects exist:

Suppose you have a LAMP (Linux, Apache, MariaDB, and PHP) [note: mysql replaced by mariadb].  
You have a working system in production using CentOS 6.2, Apache 2.2.10, MariaDB 10.0, and PHP 7.0.
Now PHP comes out with some updates but you don't want to test it out on your production system.

Suppose for example your company name is zzz.
You have your production system with a setup like zzz/p008/... the ... represents all the LAMP programs and versions.
You use my program (on your seperate dev machine) to create a new LAMP setup like zzz/p009/... 
With the new version of the LAMP system you make what ever changes you need to make the website work with the new versions.
Now you can test out your changes without affecting your production server.

After your dev testing is complete you can move the code to your test machine, and let some other person test your code.
When you all complete you can move the code to the production machine.  As your moving from the dev machine to the test machine,
you also create a script to automate the move to test, creating a few parameters that can be changed to substitute prod for test.

After your testing is complete, and you move testing is complete.
You can copy the code to your production server, and repoint everything to the new directory structure.

Ok so thats the theory of this project.  So why the separate project for the config file?
Ok here is where it gets a little more complicated.  PHP and OpenSSL get updated by different people at different times.
The newest version of OpenSSL may not work with the newest version of PHP.  XDebug may not work with the highest version of PHP either.
So this separate project is to store the configuration file where all the items work together.

I was just keeping the latest version of the configuration file, but I am up on the leading (and sometimes bleeding edge)
You may not want to be that far ahead.  So if I tag the files with version numbers starting with 0001 you can start at 001 
when I may be at 0050 or something.  You would be surprised at how fast some of these teams are pumping out updates to thier
code bases.






