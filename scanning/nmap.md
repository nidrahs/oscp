# Nmap



#### Go big

*   [ ] &#x20;List scan with nmap

    ```
     nmap -sL -oN nmap/listScan 10.x.x.x/xx
    ```
*   [ ] &#x20;Ping scan (run it with privileges)

    ```
     nmap -sn -oN nmap/pingScan 10.x.x.x/xx
    ```
*   [ ] &#x20;Look for hosts's info (name, logged-in user, MAC) with NetBIOS queries

    ```
     nbtscan -r 10.x.x.x.x
    ```
*   [ ] &#x20;Use ARP to do hosts discovery

    ```
     netdiscover -r 10.x.x.x/24
    ```
* [ ] &#x20;smbtree

#### Go small (Individual host scanning)

*   [ ] &#x20;Run a fast TCP port scan:

    ```
     nmap -F -T4 -oN nmap/fastTCPScan $IP
    ```
*   [ ] &#x20;Run a simple TCP port scan to uncover open ports

    ```
     nmap -p- -T4 -oN nmap/ezTCPScan $IP
    ```
*   [ ] &#x20;Run a simple UDP port scan to uncover open ports

    ```
     nmap -sU -n -p- -T4 -oN nmap/ezUDPScan $IP
    ```
*   [ ] &#x20;If lazy do an Aggressive scan on open ports (A = O+sC+sV)

    ```
     nmap -A -T4 -px,y,z -v -oN nmap/aggressiveScan $IP
    ```
*   [ ] &#x20;Do a version detection on TCP ports

    ```
     nmap -sV --reason -O -p- $IP
    ```
*   [ ] &#x20;Do a version detection on UDP ports

    ```
     nmap -sU -sV -n $IP
    ```
*   [ ] &#x20;Vulnerable to heartbleed?

    ```
     nmap --script ssl-heartbleed $IP
    ```
*   [ ] &#x20;Version/OS detection using other DNS servers

    ```
     nmap -v --dns-server \<DNS\> -sV --reason -O --open -Pn $IP
    ```
*   [ ] &#x20;Try identify unknown services

    ```
     amap -d $IP \<PORT\>
    ```
*   [ ] &#x20;Full vulnerability scanning with [vulnscan.nse](https://github.com/scipag/vulscan)

    ```
     nmap -sS -sV --script=/path/to/your/vulnscan.nse -oN nmap/vulnScan $IP
    ```
