# GetURL

## CATEGORY

Web Vulnerabilities

## Challenge

Your next target doesn't look so interesting, but maybe there is a hidden secret somewhere that can be used as the access key.

200 points

## Hint(s)

None used

## Solution

We found an exploit that, when we try to fetch this url:

    http://localhost.me/&<cmd>

we were able to get stuff from the machine by running cmd commands. Traversing through the directory, we were able to find the flag text file.

## Flag

    CDDC21{cMd_1Nj3Ct}
