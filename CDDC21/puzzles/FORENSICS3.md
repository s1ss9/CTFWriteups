# Default Password

## CATEGORY

Forensics

## Challenge

Members of TheKeepers got their hands on one of the GDC computers. They created a memory dump of the system as they believe it might contain some juicy information. Help them find proof.

300 points

## Hint(s)

None used

## Solution

The file given to us was a 500mb file. From the description given to us, we understand that the data given to us is a windows memory dump.

We make use of volatility to analyse the memory dump.

    0xfffffa8002226270 DumpIt.exe             3004   1848      2       46      1      1 2021-05-26 13:26:06 UTC+0000
    consoles plugin:
    ConsoleProcess: conhost.exe Pid: 3016
    Console: 0xffda6200 CommandHistorySize: 50
    HistoryBufferCount: 1 HistoryBufferMax: 4
    OriginalTitle: C:\Users\User\Downloads\DumpIt.exe
    Title: C:\Users\User\Downloads\DumpIt.exe
    AttachedProcess: DumpIt.exe Pid: 3004 Handle: 0x60
    ----
    CommandHistory: 0x35ece0 Application: DumpIt.exe Flags: Allocated
    CommandCount: 0 LastAdded: -1 LastDisplayed: -1
    FirstCommand: 0 CommandCountMax: 50
    ProcessHandle: 0x60
    ----
    Screen 0x341100 X:80 Y:300
    Dump:
    DumpIt - v1.3.2.20110401 - One click memory memory dumper
    Copyright (c) 2007 - 2011, Matthieu Suiche <http://www.msuiche.net>
    Copyright (c) 2010 - 2011, MoonSols <http://www.moonsols.com>
        Address space size:         536805376 bytes (    511 Mb)
        Free space size:           5620039680 bytes (   5359 Mb)
        * Destination = \??\C:\Users\User\Downloads\WINDOWS-90HUR58-20210526-132606.
    raw
        --> Are you sure you want to continue? [y/n] y
        + Processing...

Running this gives us the flag.

    volatility -f data --profile=Win7SP1x64 lsadump

## Flag

    CDDC21{Th1s_i$_A_L0ng_p@s$w0rd}
