# <[ ArchNoN's Anonimation Suite v3.0.7 ]> #

[desctiption] Anonimation Toolkit that ensures your linux machine's internet traffic go through a secure firewall (nftables based) and the Tor network with no IPv6 policy(leak prevention feature). Includes boot automation for the most used service managers and some useful scripts like: A simple Tor config manager, a sys daemon(prevent archnon's PID to get killed ramdomly), and a Socks5's DNS resolution tool.

- [warn] ArchNoN is a personal project developed by newmasterone27@gmail.com, if you will use it you have to know that developer wont answer in case of any issue occurs in your machine(perhaps, issues are not common, in fact, they are incredible weird).

- [warn] Fakeroot/chroot envs like: termux/proot/cointainers, usually have issues with DNS's resolution config and firewall rules that script applies, sometimes the only way to resolv DNS is by talking directly to the socks addr(can do this using resolvtool, in case of curl command).

# [ Requeriments ] # 
- [warn] Required PKGs: (bash, if not installed), all other pkgs can be managed by tool, actually.
- [warn] Extra: Full root access(to apply firewall rules and full anonimation of DNS queries with no issues)

# [ Dir Content ] #

- archnon: Main script, which applies Tor, firewall, No IPv6, anonymous DNS queries via SOCKS5, also destroys it and leaves your system as before, if you want.

- archconfig: Simple but useful Torrc Manager(can modify in almost all sense your tor configuration file).

- resolvtool: Simple SOCKS5 DNS resolution Tool(useful when trying .onion sites).

- example_bridges.txt: An example file that contains some Tor bridges from: https://bridges.torproject.org/options/en, .onion: kgclfuro65jjlivyzfmxiq2kyv5lickrl4qd.onion/options/en.

# [ Script Params/Actions ] #

- [warn] usage: archnon [ACTION]

- start --> Start ArchNoN and Apply Firewall rules.

- stop --> Stop ArchNoN and Flush Firewall rules.

- restart --> Restart ArchNoN.

- enable --> Enable ArchNoN on boot.

- disable --> Disable ArchNoN on boot.

- myip --> Show Public IP Address.

- changeid --> Change Tor Public IP Address.

- daemon --> Lauch a Daemon PID that ensures ArchNoN cant die in your system, at least you want it to(useful for automated no leaks prevention at sys level).


# [ Clone ] #
- [warn] Run as root: git clone https://github.com/0xmalaquias/ArchNoN && cd ArchNoN && chmod +x * && ./archnon


# [ Boot ] #
- [notice] Supported service managers are: Open-RC, Systemd and Runit only.
- [warn] Script detects: rc-service, rc-update, systemctl, sv, runit.
