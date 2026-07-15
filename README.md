# Neptune's Privacy Utils v3.0.10 (stable) #

[!] Junk of Bash based scripts that can provide anonimity to anyone by applying many well known extreme linux privacy concepts as: Tor/i2p networks proxy, Anonymous DNS(via socks5, tor), nftables firewall rules, sysctl calls(like full no ipv6, no respond to pings) and MAC Address spoofing, all these include a boot automation.

### [WARNINGS] ###
- 1. Numb is a personal project coded by gmasterone@duck.com, if you will use it you have to know that developer wont answer in case of any issue occurs in your machine(perhaps, issues are not common, in fact, they are very weird).

- 2. Fakeroot/containers: These kind of limmited environments usually have problems with the firewall rules that numb script applies and causes DNS resolution imposible if is not via socks5/tor only !!.

# [ Requeriments ] # 
- 3. Required PKGs: Bash, all other can be managed by any of the scripts.
- 4. Extra: Full root access(as i said before, to apply firewall with no issues and full sys DNS).

# [ Clone ] #
- As root: git clone https://github.com/malaquiasxv/numb && cd numb && chmod +x * && ./make_it_work
