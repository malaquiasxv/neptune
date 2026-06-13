# < --- [ TheOnionBox ] --- >
# [DESCRIPTION] #
[!] Shell based script of Tor+Firewall+No IPv6 for linux distros, (uses Tor and iptables based firewall rules, examples below).

# [About Services] #

[!] Yes, sometimes you'll be able to run it on boot, supported managers are: Open-RC, Systemd and Runit, at this moment, maybe i will add some more then.

# [About Firewall] # 

[!] As i said before, rules are iptables based, you'll be able to block echo-request (which prevents icmp(pings) protocol based floods/DoS against your host machine), DROP each packet that doesnt match any rule and have communication by using loopback's(localhost) interface that tor daemon uses to work.

[*] For Example(some of lo+tor rules here): 
- iptables -A INPUT -i lo -j ACCEPT <-- This accept input via lo(you send a packet).
- iptables -A OUTPUT -o lo -j ACCEPT <-- This accept output via lo(you recieve a packet).
- iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT <--- Only if a TCP/UDP handshake occurs and returns any of those states (here is when your host machine talks to a tor relay/bridge).
- iptables -A OUTPUT -m conntrack --ctstate NEW,ESTABLISHED,RELATED -j ACCEPT <--- output version of before's rule
- iptables -A INPUT -i lo -p icmp --icmp-type echo-request -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT <--- ICMP version of before's rules about TCP/UDP.
- iptables -A OUTPUT -o lo -p icmp --icmp-type echo-request -m conntrack --ctstate NEW,ESTABLISHED,RELATED -j ACCEPT <--- ICMP version of before's rules about TCP/UDP.
- iptables -A INPUT -p icmp --icmp-type echo-request -j DROP <--- DROP ICMP that is not being sended via loopback.
- iptables -A OUTPUT -p icmp --icmp-type echo-request -j DROP <--- DROP ICMP that is not being recieved via loopback.
- iptables -A OUTPUT -m owner --uid-owner 43(which is the Tor user id in some linux distros) -j ACCEPT <--- Allows Tor user to comunicate with us.
- ... <--- some other rules about localhost's ports that tor controls && some allowed private cidr ranges(like allow your home's router to comunicated with you)
- iptables -P OUTPUT DROP <--- DROP everything else.
- iptables -P FORWARD DROP <--- DROP everything else.
- iptables -P INPUT DROP <--- DROP everything else.

[!] It just allows the communication via loopback+Tor user only and that will simply DROP everything else.

# [About Dependencies, Usage, Recommended actions] #
[!] Required PKGs: 
- openbsd-netcat curl tor iptables iproute2 coreutils util-linux bash iptables-nft nftables sudo

[!] Script actions: --start, --stop, --restart, --boot-enable, --boot-disable, --myip, --changeid, --set-bridges --reset-config, --help.

[!] To use it right now: 
- Note: always run this as root, (if you have sudo/git installed in your system)
- git clone https://github.com/0xmalaquias/TheOnionBox && cd TheOnionBox && chmod +x * && ./onionbox help

[!] In addition:
- Recommended: Configure a secure non standard/common browser(like tor's one, sometimes it is easy). 
- Recommended: Use Tor bridges or a VPN connection, just in case you want to be 100% sure that your ISP wont be able to see your connection nodes!!
