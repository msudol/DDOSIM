
# DDOSIM:  Layer 7 DDoS Simulator v0.3
# Author:  Adrian Furtuna  <adif2k8@gmail.com>
# v0.3 Updates: Matt Sudol <github.com/msudol>


About
-----
The goal of this repository is to update DDOSIM to work with newer libraries and on 
64-bit architecture, the original v0.2 requires some outdated packages and will only 
run on 32-bit systems. 


Requirements
------------
DDOSIM currently requires a system with 32-bit architecture. Kali Linux 32-bit works well.  

Additionally, the following libraries are required: libpcap-dev and libnet0. Libnet0 is 
deprecated but may be installed by downloading and installing the following packages:

    wget http://launchpadlibrarian.net/1302421/libnet0_1.0.2a-7_i386.deb
    wget http://launchpadlibrarian.net/1302422/libnet0-dev_1.0.2a-7_i386.deb
    dpkg -i libnet0_1.0.2a-7_i386.deb
    dpkg -i libnet0-dev_1.0.2a-7_i386.deb

Install libpcap-dev with: apt-get install libpcap-dev


Installation
------------
./configure
make
make install


Usage
-----
./ddosim
     -d IP           Target IP address
     -p PORT         Target port
    [-k NET]         Source IP from class C network  (ex. 10.4.4.0)
    [-i IFNAME]      Output interface name
    [-c COUNT]       Number of connections to establish
    [-w DELAY]       Delay (in milliseconds) between SYN packets
    [-r TYPE]        Request to send after TCP 3-way handshake. TYPE can be HTTP_VALID or HTTP_INVALID or SMTP_EHLO
    [-t NRTHREADS]   Number of threads to use when sending packets (default 1)
    [-n]             Do not spoof source address (use local address)
    [-v]             Verbose mode (slower)
    [-h]             Print this help message


Documentation
-------------
http://stormsecurity.wordpress.com/2009/03/03/application-layer-ddos-simulator/
