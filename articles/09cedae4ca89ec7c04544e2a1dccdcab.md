## How to Find my IP Address using Command Line on Linux

![thumbnail](https://raw.githubusercontent.com/neoslab/tutorials/master/thumbnails/09cedae4ca89ec7c04544e2a1dccdcab-1920x1080.jpg "Thumbnail")

How do I find my public IP address on the Linux and OS X Unix command line to use with my bash shell script without using a third party web site? Is there a command-line option which will show my dynamic IP address on a Ubuntu or Fedora Linux?

There are many ways to find out your public IP address or wan (Wide Area Network) IP on a Linux or Unix-like operating systems such as FreeBSD, OpenBSD, NetBSD, Apple OS X, and others.

**Source:** [cyberciti.biz](https://www.cyberciti.biz/faq/how-to-find-my-public-ip-address-from-command-line-on-a-linux/)

* * *

###### EXPLAIN IP ADDRESSES

An IP is short for Internet Protocol. It is used to identify computers or mobile devices on the Internet. Each device connected to the Internet has an IP address. The IP addresses can be used to personalize information.

* * *

###### DIG COMMAND

Use Dig command for determining my public IP address:

Open the Terminal application then type the following dig (domain information groper) command on a Linux, OS X, or Unix-like operating systems to see your public IP address assigned by the ISP:

```bash
dig +short myip.opendns.com @resolver1.opendns.com
```

Or

```bash
dig TXT +short o-o.myaddr.l.google.com @ns1.google.com
```

You should see your IP address on the screen. This is the fastest way to find out your IP address without using 3rd party site.

* * *

###### STORE IP IN A SHELL VARIABLE

**Syntax**

```bash
#!/bin/bash
myip="$(dig +short myip.opendns.com @resolver1.opendns.com)"
echo "My WAN/Public IP address: ${myip}"
```

**Output**

```none
My WAN/Public IP address: 74.86.144.194
```

* * *

###### USE 3RD PARTY WEBSITES

Please note that I do not recommend following third-parties' curl/wget method due to security reasons.

```bash
curl ifconfig.me
curl icanhazip.com
curl ipecho.net/plain
curl ifconfig.co
```
