# Broken System

## Category

OSINT

## Challenge

The CryptIT Banking and Consulting company suspects that the GDC is attacking its email systems. They need your help to fix the misconfiguration.

200 points

## Hint(s)

None used

## Solution

With a DNS lookup, we found 2 namepaces.

Performing a zone transfer on the second NS yields us this:

    └─$ dig axfr @128.199.253.39 cryptit.biz

    ; <<>> DiG 9.16.15-Debian <<>> axfr @128.199.253.39 cryptit.biz

    ; (1 server found)

    ;; global options: +cmd

    cryptit.biz. 86400 IN SOA ns1.cryptit.biz. hostmaster.cryptit.biz. 2021061901 604800 86400 2419200 86400

    cryptit.biz. 86400 IN A 165.22.102.81

    cryptit.biz. 86400 IN NS ns1.cryptit.biz.

    cryptit.biz. 86400 IN NS ns2.cryptit.biz.

    cryptit.biz. 86400 IN TXT "v=spf1 a mx ?all nice try, but this is not your flag"

    dmarc.cryptit.biz. 86400 IN TXT "v=DMARC; p=none; <strong>CDDC21{\_10x_f0r_yOur_Serv!ce}</strong>"

    ns1.cryptit.biz. 86400 IN A 159.65.8.127

    ns2.cryptit.biz. 86400 IN A 128.199.253.39

    www.cryptit.biz. 86400 IN A 165.22.102.81

    cryptit.biz. 86400 IN SOA ns1.cryptit.biz. hostmaster.cryptit.biz. 2021061901 604800 86400 2419200 86400

    ;; Query time: 44 msec

    ;; SERVER: 128.199.253.39#53(128.199.253.39)

    ;; WHEN: Wed Jun 23 22:30:10 EDT 2021

    ;; XFR size: 10 records (messages 1, bytes 387)

## Flag

    CDDC21{\_10x_f0r_yOur_Serv!ce}
