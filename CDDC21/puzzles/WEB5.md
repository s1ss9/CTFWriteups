# Tokenization

## CATEGORY

Web Vulnerabilities

## Challenge

The next server was used as a user validation API. Could you manipulate it to your side?

## Hint(s)

1. You don't need to find the admin user. Enter any username and take a look at the server's response headers.

## Solution

The hint was useless to us as we had already found the token by the time we used the hint.

We uploaded a php file with a webshell using the token, which was accepted, and this gave us the flag.

## Flag

    CDDC21{s3r1Alize_mY_PHPP}
