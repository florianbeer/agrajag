# Agrajag
A daily rotating MySQL backup script

Copyright (c)2015 by [Florian Beer](https://github.com/florianbeer)

Version 1.01


This script comes with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to redistribute it
under certain conditions. See CC BY-NC-SA 4.0 for details.
https://creativecommons.org/licenses/by-nc-sa/4.0/

## Usage
Agrajag has to be configured in the script itself:
```
TARGET    The location of your backup directory
CONF      The location of a MySQL options file including at least a username and password
IGNORE    Ignore these lines of mysql's SHOW DATABASES output. Separated by a pipe symbol "|"
RETAIN    Number of days after which old backups will be deleted
```
Default values are set in the script already, but you might have to change them to reflect your system and setup.

Calling Agrajag from cron every night can be achieved with the following line:
```
30 1 * * *  /usr/local/bin/agrajag > /dev/null
```
This will call the script each day at 1:30am, supress standard output but mail any errors that occured during execution to root.
