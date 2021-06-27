# Mounting

## CATEGORY

Reconnaissance

## Challenge

I don't know what this server is used for, it doesn't look like a web server, but I'm sure that the GDC uses this machine for their hostile activities.

## Hint(s)

None used

## Solution

We first run a nmap scan on the IP address:

    21/tcp open ftp vsftpd 3.0.3
    22/tcp open ssh OpenSSH 8.2p1 Ubuntu 4ubuntu0.2 (Ubuntu Linux; protocol 2.0)
    111/tcp open rpcbind 2-4 (RPC #100000)
    | rpcinfo:
    ...
    139/tcp open netbios-ssn Samba smbd 4.6.2
    445/tcp open netbios-ssn Samba smbd 4.6.2
    2049/tcp open nfs_acl 3 (RPC #100227)

Cheking mounts gives us /var/nfs/backup but we were unable to mount to /var/nfs/backup with samba.

However, we found out that we were supposed to mount to nfs instead of samba, and managed to get the flag from there.

    sudo mount -t nfs 178.128.118.134:/var/nfs/backup /mnt/smb

## Flag

    CDDC21{?}
