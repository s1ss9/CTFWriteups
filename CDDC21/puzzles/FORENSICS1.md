# Look Closer

## CATEGORY

Forensics

## Challenge

The resistance managed to find a suspicious file. They believe it contains some useful data. Unfortunately, they weren't able to retrieve it. Help them find what they are looking for.

100 points

## Hint(s)

None used

## Solution

The file given to us consists of a string which looked like base64.

We convert the output of the string file into base64 and pipe it into another file. This happens to be in hexdump, and we conveniently have xxd to help us reverse hexdump to a normal string.

Based on the other bits of the hex, we are able to determine that this file is an ELF file although the magic bytes were given as CDDC. We used a [hexeditor](https://hexed.it/) to change the magic bytes of the file from CDDC to .ELF, which doesn't increase the size.

From there, we are able to run the file to get our flag.

## Flag

    CDDC21{C@n_Y0u_F1nD_mE?}
