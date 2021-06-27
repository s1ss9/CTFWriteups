# Opening the Gate

## CATEGORY

Linux

## Challenge

One of TheKeepers has successfully obtained what seems to be one of the GDC private servers. He has sent me the image and another file, but unfortunately, I'm not great with Linux. I think you're the one for this mission.

<br>

**Target IP: 13.213.192.83**

<br>

**Link: http://157.230.245.61/0x0302/nQE0XQ/m1/file.zip**

<br>

**SHA256: 441bddcc9d80edd976573a57b53cc63eeac02151cc3086b9dbf556f9f2bbcd6a**

50 points

## Hint(s)

None used

## Solution

Using the bot1 key provided, we ssh into the ip address with this format:

ssh 13.213.192.83 -i bot1.key

Then, we enter the provided passphrase to gain access.

In the machine, we can simply cat the flag.txt to obtain the bot1 flag.

## Flag

    CDDC21{S$H_keYs_are_Be!ter_than_PaSSw0rds}
