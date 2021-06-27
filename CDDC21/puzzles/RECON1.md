# UnKnown

## CATEGORY

Reconnaissance

## Challenge

This GDC's public server seems to run an unknown service. I tried to enumerate this service, but I can't find its version. Find this strange service and see if you can find its version.

200 points

## Hint(s)

None used

## Solution

We first scan the IP address with nmap to get this:

    PORT STATE SERVICE
    21/tcp open ftp
    22/tcp open ssh
    666/tcp open doom
    8007/tcp closed ajp12
    8080/tcp open http-proxy
    41511/tcp closed unknown

At first glance, `666 | doom` looks suspicious

Scanning 666 in greater detail reveals this:

    | fingerprint-strings:
    | NULL:
    | file.tarUT
    | CpwKpw
    | YHpw
    | \xcb.
    | )n<~^
    | a'ufv
    | .qV*a4
    | 5@u0
    | T'dp
    | \x04m
    | \xb2
    | \x11.
    | }}so
    | ~8VB

## Flag

    CDDC21{Y0u_Figu4ed_IT_0UT}
