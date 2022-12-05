# Autorecon

```
autorecon <HOST>

autorecon -t <HOSTS FILE>

autorecon -cs 5 <HOST> //concurrent scans, default 10

autorecon <HOST> --single-target //scan witout creating directory for host

autorecon <HOST> --heartbeat 5 //default 60, how often output is updating

autorecon <HOST> --nmap <nmap option ex. -sV> //replace autorecon default '-vv, –reason, -Pn' with given options

autorecon <HOST> --nmap-append <option> //append nmap option

autorecon -v/-vv <HOST> //add verbosity

autorecon <HOST> --only-scans-dir //don't create directories for services
```





#### **Results**



*   #### **Enum4Linux Scan**

    &#x20;results/\<targetname>/scans/enum4linux.txt
*   #### **SMBMap Scan**

    results/\<targetname>/scans/smbmap-share-permissions.txt
*   #### **SMTP Scan**

    &#x20;results/\<targetname>/scans/tcp\_25\_smtp\_user-enum.txt
*   #### **WhatWeb Scan**

    results/\<targetname>/scans/tcp\_8180\_http\_whatweb.txt
*   #### **XML Results**

    results/\<targetname>/scans/xml/tcp\_21\_ftp\_nmap.xml
*   #### **Nikto Scan**

    ```
    cat ~/results/192.168.126.132/scans/tcp_8180_http_nikto.txt
    ```
*   **Web Services Screenshots**

    ```
    file:///root/results/192.168.126.132/scans/tcp_8180_http_screenshot
    ```

