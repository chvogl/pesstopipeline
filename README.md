PESSTO NTT Pipeline Docker Image
====================

Installation:
====================

This script activates a Docker container with an iraf/pyraf installation and the pessto quickreduction pipeline ( see https://github.com/svalenti/pessto ). To activate the script, a working installation of Docker is required.

First, activate the option ‘Allow connections from network clients’ in your XQuartz settings.

To conveniently run the script, create an alias in the config file of your preferred shell, e.g.

    alias pyraf="/Users/<username>/path/to/pesstopipeline/pyraf_pesstopipeline"

Then run the script by typing 

    pyraf
    
If you want to use a different command to start the docker container, simply name the alias differently, e.g. 

    alias custom_pyraf_start_command="/Users/<username>/path/to/pesstopipeline/pyraf_pesstopipeline"

The script automatically mounts the folder from which it is run to /home/pessto/data/<folder_from_which_it_is_started>.

    root@9f1e3c0c7042:/# 
    root@9f1e3c0c7042:/# cd home/pessto/data/
    root@9f1e3c0c7042:/home/pessto/data
    
You can run `PESSTOFASTSPEC` or `pyraf` from any directory:

    root@9f1e3c0c7042:/home/pessto/data# pyraf
    setting terminal type to 'xterm' ...

      NOAO/IRAF PC-IRAF Revision 2.16.1 EXPORT Mon Oct 14 21:40:13 MST 2013
        This is the EXPORT version of IRAF V2.16 supporting PC systems.


      Welcome to IRAF.  To list the available commands, type ? or ??.  To get
      detailed information about a command, type `help <command>'.  To run  a
      command  or  load  a  package,  type  its name.   Type  `bye' to exit a
      package, or `logout' to get out  of the CL.    Type `news' to find  out
      what is new in the version of the system you are using.

      Visit http://iraf.net if you have questions or to report problems.


      ***  Using global login file:  /root/iraf/login.cl
      The following commands or packages are currently defined:

    clpackage/:
     clpackage/     images/         noao/           proto/          user/
     dataio/        language/       obsolete/       softools/       utilities/
     dbms/          lists/          plot/           system/         vo/
    PyRAF 2.1.14 Copyright (c) 2002 AURA
    Python 2.7.12 Copyright (c) 2001-2016 Python Software Foundation.
    Python/CL command line wrapper
      .help describes executive commands
    -->

Note: The stecf iraf package is no longer available on github. Among others, the PESSTOEFOSCPHOT method depends on stecf and thus doesn't work with this container.
