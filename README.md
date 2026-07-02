# Archnon Privacy Utils v3.0.10 #

[!] Junk of Bash based scripts that can provide anonimity to anyone by applying many well known extreme linux privacy concepts as: Tor advanced proxying, Anonymous DNS(via socks5, tor), nftables firewall rules, sysctl calls(like full no ipv6, no respond to pings) and MAC Address spoofing, all these include a boot automation and daemons.

### [WARNINGS] ###
- 1. ArchNoN is a personal project developed by newmasterone27@gmail.com, if you will use it you have to know that developer wont answer in case of any issue occurs in your machine(perhaps, issues are not common, in fact, they are very weird).

- 2. Fakeroot/limited envs like: termux/proot/docker, usually have problems with firewall rules that script applies and breaks DNS sock5 only !!.

# [ Requeriments ] # 
- 3. Required PKGs: Bash, all other can be managed by any of the scripts.
- 4. Extra: Full root access(as i said before, to apply firewall with no issues and full sys DNS).

# [ Clone ] #
- As root: git clone https://github.com/0xmalaquias/Archnon && cd Archnon && chmod +x * && ./archnon
