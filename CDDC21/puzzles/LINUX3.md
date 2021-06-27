# Another Path

## CATEGORY

Linux

## Challenge

You must continue and pwn this machine. Please don't bother me with all those bots. I know they're connected somehow. If you feel stuck, try to take another path.

300 points

## Hint(s)

None used

## Solution

There's a flag.txt file in bot3's home directory.

The flag.txt file is owned by bot4, who also owns another binary with a bot4 SUID bit in /usr/local/bin/systeminfo. We find a writable directory with the command

    find / -writable 2>/dev/null

Using /dev/shm,

We find a SUID binary owned by bot4 which runs 2 absolute path commands and one relative path command (id).

We are able to abuse this information by creating a id binary in /dev/shm, and adding the following bash code.

    #!/bin/bash
    /bin/sh

This allows us to get a shell as bot4 and we are able to read the file in bot3's home directory.

## Flag

    CDDC21{SU1d_!s_Qu1Te_DangeRouS}
