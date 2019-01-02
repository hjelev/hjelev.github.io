---
layout: post
title: DNS Filtering
date:   2019-01-02
categories: windows
---
# Block ads and protect your network from malware by changing your DNS provider.

## Ad Guard

Adguard.com offers ads filtering plus malware protection.

<http://dns.adguard.com>{:target="_blank"}


* use these DNS servers if you want ads blocking and malware protection:

176.103.130.130

176.103.130.131

* ads blocking, malware protection and "Family protection" servers.

176.103.130.132

176.103.130.134

## Alternate DNS

Ad Free Web browsing

<https://alternate-dns.com/>{:target="_blank"}

23.253.163.53

198.101.242.72

## PrivateDNS - EPSILON EIGHT 

Block over 114k advertisement and malware-serving domains

https://www.epsiloneight.com/private-dns

138.68.250.168 

## CleanBrowsing DNS

<https://cleanbrowsing.org/filters>{:target="_blank"}


They have 3 free content filters available via IPv4 and IPv6. Choose the one that fits your needs the most. 

All their IP addresses accept DNS request to the standard port 53 and 5353. DNS over TLS is available over port 853 and DNScrypt over port 8443.

1. Security Filter  185.228.168.9       Malicious domains blocked (phishing, malware).
2. Adult Filter     185.228.168.10      Adult domains blocked; Search Engines set to safe mode; +Security Filter
3. Family Filter    185.228.168.168     Proxies, VPNs & Mixed Adult Content blocked; Youtube to safe mode; +Adult


## Open DNS
<https://www.opendns.com/setupguide/#familyshield>{:target="_blank"}

OpenDNS Family Shield

Pre-configured to block adult content — set it & forget it

208.67.222.123
208.67.220.123


## Quad 9
<https://www.quad9.net>{:target="_blank"}

Quad 9 provides malware and malicious domains protection - there is no ads blocking.

Select “Use the following DNS server addresses” and enter 9.9.9.9 into the Preferred DNS server box. For the Alternative DNS server enter 149.112.112.112

If you are using IPv6 enter 2620:fe::fe into the Preferred DNS server box.

Optional: You can add 2620:fe::9 as the alternative in the list.

## Pi-hole®: A black hole for Internet advertisements
<https://pi-hole.net/>{:target="_blank"}

This is a self hosted option. You can host pi-hole on a raspberry pi, docker container or VM and maintain your own block lists.
You can also use this with one of the DNS providers mentioned above.

<https://firebog.net/> {:target="_blank"} - block lists to use with pi-hole


## Other DNS providers
* Google 8.8.8.8: Private and unfiltered. Most popular option.
* CloudFlare 1.1.1.1: Private and unfiltered. New player.
* Quad9 9.9.9.9: Private and security aware. New player that blocks access to malicious domains.
* OpenDNS 208.67.222.222: Old player that blocks malicious domains and offers the option to block adult content.
* Norton DNS 199.85.126.20: Old player that blocks malicious domains and is integrated with their Antivirus.
* CleanBrowsing 185.228.168.168: Private and security aware. New player that blocks access to adult content.
* Yandex DNS 77.88.8.7: Old player that blocks malicious domains. Very popular in Russia.
* Comodo DNS 8.26.56.26: Old player that blocks malicious domains.
