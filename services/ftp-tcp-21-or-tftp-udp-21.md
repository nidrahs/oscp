# FTP (TCP 21) | TFTP (UDP 21)

nmap check

```
 nmap --script ftp-anon,ftp-bounce,ftp-libopie,ftp-proftpd-backdoor,ftp-vsftpd-backdoor,ftp-vuln-cve2010-4221,tftp-enum -Pn -oN nmap/ftpVuln -p 21 $IP
 
 nmap --script=*ftp* --script-args=unsafe=1 -p 20,21 $IP
```



Anonymous access and try upload

```
ftp ip
ftp> USER anonymous
ftp> PASS anonymous/empty password
ftp> put file //test uploading
ftp> get file//test download

```



Download all files

```
 wget -r ftp://user:pass@$IP/
 wget -r --user="user" --password="secret" ftp://$IP/
```



users enumerate

[https://github.com/pentestmonkey/ftp-user-enum](https://github.com/pentestmonkey/ftp-user-enum)

```bash
ftp-user-enum.pl -U users.txt -t $ip //solaris

ftp-user-enum.pl -M iu -U users.txt -t $ip //ftpd
```



default credentials

```
 hydra -s <PORT> -C usr/share/wordlists/ftp-default-userpass.txt -u -f $IP ftp
```



bruteforce attacks

```
// for know username
hydra -l $user -P /usr/share/john/password.lst ftp://$ip:21

hydra -l $user -P /usr/share/wordlistsnmap.lst -f $ip ftp -V

medusa -h $ip -u $user -P passwords.txt -M ftp

```

