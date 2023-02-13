# mobile-number-portability-lookup
Mobile Number Portability Lookup

# Client Execute..
```console
dig @mnp.hopto.org -p3054 2.1.8.3.4.5.3.9.4.1.6.e164.arpa IN NAPTR
```

# Client Result..

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

#  Server

[Screenshot Server](/screenshots/dns_dist_screenshot.png)
<img src="/screenshots/dns_dist_screenshot.png"></img>

#  Client
[Screenshot Client](/screenshots/dns_dist_dig.png)
<img src="/screenshots/dns_dist_dig.png"></img>
<hr/>
