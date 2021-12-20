## Category

Crypto

## Challenge

Decrypt the given data:

    OJZXG4TBMBGHCMSEORRGCMCQIQYEIRJ2MBQDAOR7GATEIYTONZHAU===

200 points

## Hint(s)

None used

## Solution

Strongly hinted by the 3 equal signs at the end of the string and the name of the challenge, we first apply base 32 to decode the data, resulting in the following:

    rssra`Lq2Dtba0PD0DE:``0:?0&DbnnN
    
It still looks like a mess but notice that it starts with 'rssr' which resembles encoding 'cddc' with a ROT cipher. We thus decode it with ROT47 and obtain the flag.

## Flag

    CDDC21{BasE32_!s_sti11_in_Us3??}
