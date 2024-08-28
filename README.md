Redirect connections from different ports at one ipv4 address to unique random ipv6 address from \64 subnetwork. Based on 3proxy



## Requirements
- Centos 7
- Ipv6 \64

## Installation
Use on   Centos7 setup only. In 9 nft_compat is unmaintained.

1. `bash <(curl -s "https://raw.githubusercontent.com/quayvlog/proxyv6/main/install.sh")`

1. After installation dowload the file `proxy.zip`
   * File structure: `IP4:PORT:LOGIN:PASS`






SECOND SETUP 

 ## Requirements
- AlmaLinux8
- Ipv6 \64


yum update -y
yum -y install curl wget nano make

wget https://raw.githubusercontent.com/jackalsoft/multiipv6/main/install.sh

chmod +x /root/install.sh
bash /root/install.sh {IPV6Value}

Example : IPV6Value can be taken from IPV6Range. Consider this IPV6Range 2600:3c06:e001:47::/64
Only cut 4, : delimited range 2600:3c06:e001:47 and pass it as param.
bash /root/install.sh 2600:3c06:e001:47

After installation dowload the file proxy.zip File structure: IP4:PORT:LOGIN:PASS You can use this online util to change proxy format as you like

Finally allow the port ranges in firewall
firewall-cmd --permanent --zone=public --add-port=10000-11000/tcp

increase ulimits
ulimit -n 10000
ulimit -Hn 10000

restart the server and start 3proxy using command
/etc/init.d/3proxy start
before connecting to proxy.
