# AccessKey

## CATEGORY

Web Vulnerabilities

## Challenge

Your next target doesn’t look so interesting, but maybe there is a hidden secret somewhere that can be used as the access key.

200 points

## Hint(s)

None used

## Solution

In the target, we find a secret.js file which has this line of code inside:

    var pass = unescape("unescape%28%22String.fromCharCode%252867%252C68%252C68%252C67%252C50%252C49%252C123%252C95%252C32%252C68%252C101%252C48%252C98%252C102%252C117%252C36%252C99%252C97%252C116%252C101%252C100%252C45%252C70%252C33%252C97%252C71%252C95%252C125%2529%22%29");

We decode the character codes to get the flag: CDDC21{ De0bfu$cated-F!aG}

## Flag

    CDDC21{ De0bfu$cated-F!aG}
