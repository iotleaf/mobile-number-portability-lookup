# mobile-number-portability-lookup
Mobile Number Portability Lookup

<img src="/screenshots/dns_dist_screenshot.png" width="400"></img>
<br/>

# Client:

## Client Execute..
```console
dig @mnp.hopto.org -p3054 2.1.8.3.4.5.3.9.4.1.6.e164.arpa IN NAPTR
```

## Client Result..

```console
; <<>> DiG 9.16.37-Debian <<>> @mnp.hopto.org -p3054 2.1.8.3.4.5.3.9.4.1.6.e164.arpa IN NAPTR
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 11283
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;2.1.8.3.4.5.3.9.4.1.6.e164.arpa. IN	NAPTR

;; ANSWER SECTION:
2.1.8.3.4.5.3.9.4.1.6.e164.arpa. 3600 IN NAPTR	10 100 "u" "E2U+pstn:tel" "!^(.*)$!tel:\\\\1\\;mcc=310\\;mnc=012!" .

;; Query time: 88 msec
;; SERVER: 213.171.214.151#3054(213.171.214.151)
;; WHEN: Mon Feb 13 13:00:34 GMT 2023
;; MSG SIZE  rcvd: 116
```

<hr/>

# Screenshots
The server would normally run on a <b>headless</b> system (i.e. no screen, keyboard or mouse) via the <b>dns_daemon</b> application.
<br/><br/>
The system also provides <b>GUI</b> tools for systems with a screen attached (or <b>VNC</b>) to make testing easier.
<br/>
These screenshots show both the daemon and GUI applications.

##  Server Application(s)

[Screenshot Server](/screenshots/dns_dist_screenshot.png)
<img src="/screenshots/dns_dist_screenshot.png"></img>

##  Client Application (dig)
[Screenshot Client](/screenshots/dns_dist_dig.png)
<img src="/screenshots/dns_dist_dig.png"></img>
<hr/>

# linux daemon
## install

### dns_daemon.ini
Modify address and port number..
```console
[config]
address=192.168.1.75
port=3053 
```
<hr/>

### Command line install and start

```console
cd /daemon/
sudo ./dns_daemon      -install
sudo systemctl enable  dns_daemon
sudo systemctl start   dns_daemon
sudo systemctl status  dns_daemon
```

### Log 
```console
15:12:08 Log created
15:12:08 Daemon received stop signal
15:12:08 Daemon worker thread destroyed
15:12:08 Daemon stopped
15:12:14 STARTED
15:12:14 Daemon worker thread created
15:12:14 Daemon worker thread executing
15:12:44 Binding 192.168.1.75 with 3053
```

## manage

```console
sudo systemctl enable  dns_daemon
sudo systemctl start   dns_daemon
sudo systemctl status  dns_daemon
sudo systemctl stop    dns_daemon
sudo systemctl disable dns_daemon
```


## uninstall

```console
cd /daemon/
sudo ./dns_daemon      -uninstall   
```

