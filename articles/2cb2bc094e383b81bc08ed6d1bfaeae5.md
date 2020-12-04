## Getting Started with Metasploit for Ethical Hacking

![thumbnail](https://raw.githubusercontent.com/neoslab/tutorials/master/thumbnails/2cb2bc094e383b81bc08ed6d1bfaeae5-1920x1080.jpg "Thumbnail")

**Metasploit** is one of the most powerful exploitation tools. Most of its resources can be found at [Metasploit](https://www.metasploit.com). It comes in two versions, **commercial** and **community edition**. There are no major differences in the two versions, so in this tutorial, we will be mostly using the Community version of Metasploit.

As an Ethical Hacker, you will be using **Kali Linux** which has the Metasploit community version embedded in it along with other ethical hacking tools. But if you want to install Metasploit as a separate tool, you can easily do so on systems that run on Linux, Windows, or Mac OS X.

The hardware requirements to install Metasploit are:

- 2 GHz+ processor
- 1 GB RAM available
- 1 GB+ available disk space

Mostly Metasploit is used from the terminal. To open it simply execute the following command:

```bash
msfconsole
```

After Metasploit starts, you will see the below screen. Highlighted in yellow is the version of Metasploit.

![image-1](https://raw.githubusercontent.com/neoslab/tutorials/master/medias/2cb2bc094e383b81bc08ed6d1bfaeae5-1.png "Image-1")

* * *

###### EXPLOITS OF METASPLOIT

For this article, we will pretend that from Vulnerability Scanner, we found that the Linux machine that we have for the test is vulnerable to FTP service. Now, we will use the exploit that can work for us. To do so we will use an exploit called "`vsftpd_234_backdoor`". This is given for information purposes only to understand how Metasploit works.

```bash
msf > use exploit/unix/ftp/vsftpd_234_backdoor
```

**Output**

![image-2](https://raw.githubusercontent.com/neoslab/tutorials/master/medias/2cb2bc094e383b81bc08ed6d1bfaeae5-2.png "Image-2")

Then type "`msf > show options`" to see what parameters you have to set to make it functional. As shown in the following screenshot, we have to set **RHOST** as the "target IP".

![image-3](https://raw.githubusercontent.com/neoslab/tutorials/master/medias/2cb2bc094e383b81bc08ed6d1bfaeae5-3.png "Image-3")

We type "`msf > set RHOST 192.168.1.101`" and "`msf > set RPORT 21`".

![image-4](https://raw.githubusercontent.com/neoslab/tutorials/master/medias/2cb2bc094e383b81bc08ed6d1bfaeae5-4.png "Image-4")

Then, type "`msf > run`". If the exploit is successful, then it will open one session that you can interact with.

* * *

###### METASPLOIT PAYLOADS

Metasploit payloads can be of three types:

* **Singles:** Singles are very small and designed to create some kind of communication, then move to the next stage. For example, just creating a user.
* **Staged:** It is a payload that an attacker can use to upload a bigger file onto a victim system.
* **Stages:** Stages are payload components that are downloaded by Stagers modules. The various payload stages provide advanced features with no size limits such as Meterpreter and VNC Injection.

Payload, in simple terms, is simple scripts that the hackers utilize to interact with a hacked system. Using payloads, they can transfer data to a victim system.

* * *

###### PAYLOAD USAGE − EXAMPLE

We use the command "`show payloads`". With this exploit, we can see the payloads that we can use, and it will also show the payloads that will help us upload / execute files onto a victim system.

To set the payload that we want, we will use the following command:

```bash
msf > set PAYLOAD payload/path
```

Set the host and port to listen (LHOST, LPORT) which are the **attacker IP** and **port**. Then set remote host and port (RPORT, LHOST) which are the **victim IP** and **port**. When you are ready, simply type "exploit" to create a session if the targeted host is vulnerable to the exploit you selected.
