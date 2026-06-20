# < --- [ ArchNoN Project ] --- > #
[*] Bash based Anonimation tool that uses Tor's strongest privacy configuration, including a no IPv6 policy and a secure nftables firewall stack for linux distros.

[warn] ArchNoN is a personal project developed by 0xmalaquias@github.com, if you will use it you have to know that developer wont answer in case of any issue occurs in your machine(perhaps, issues are not common, in fact, they are incredible weird)

[*] If you'll use it on a fakeroot/chroot env like proot/nethunter, on termux, you have to know that script will block you entirelly to use curl normally, (because it wont be able to apply firewall, only if you are rooted), to resolv any link you must use tool’s "link" param, or give to curl the param: --socks5-hostname 127.0.0.1:9150.

# [ Requeriments ] # 
[*] Required PKGs: 
- openbsd-netcat curl tor coreutils util-linux bash nftables/iptables sudo(some pkg names are different, depends entirely on your distro’s pkg manager).

# [ Content ] #

- archnon >> Modern version of the script, it uses the modern, clean, faster alternative to iptables: nftables. Sometimes is much faster than old iptables(better on all sense).

- example_bridges.txt >> It is just a list of tor bridges, you can grab them from here: https://bridges.torproject.org/options/en, or, if you prefer .onion: kgclfuro65jjlivyzfmxiq2kyv5lickrl4qd.onion/options/en

- try-dot-onion >> Try to curl .onion addresses(this script comes with some of them, for example: duckduckgo, hiddenwiki, etc) by running ./try-dot-onion, uses default's socks5 proxy address(127.0.0.1:9150), it might fail if you use a different address/tor is not running.

- make_it_work >> ./make_it_work, just moves the shell, scripts to your /usr/bin dir(run as root).

# [ Actions ] #

[0] start <-----> Start ArchNoN and Applies Firewall rules.

[1] stop: <-----> Stop ArchNoN and Flushes Firewall rules.

[2] restart: <-----> Restart ArchNoN and Firewall rules.

[4] boot-enable: <-----> Enables ArchNoN to start on boot.

[5] boot-disable: <-----> Disables ArchNoN to start on boot.

[6] myip: <-----> Show Your Public IP Address.

[7] changeid: <-----> Change Your Public IP Address.

[9] bridges: <-----> Load a custom Tor bridges configuration for ArchNoN, usage: archnon(or '-nft') bridges <file> <kind> <bridges_binary>.

[10] config-reset: <-----> Reset Tor's configuration file (/etc/tor/torrc) to ArchNoN default.

[11] config-show: <-----> Shows configuration files touched by ArchNoN !! (/etc/tor/torrc, /etc/resolv.conf).

[12] link: <-----> Resolves .onion addresses.

[13] --help|-help|help|-h: <-----> Prints this help page.

# [ Clone ] #
- As root: git clone https://github.com/0xmalaquias/ArchNoN && cd ArchNoN && chmod +x * && ./make_it_work

# [ Boot ] #
[*] Supported service managers are: Open-RC, Systemd and Runit only.

# [ Recommended ] #

- Configure a Web Browser(prefer tor's one, it is very easy): You would have to force its internet connection to the socks5 proxy address/ports, ex(if torbrowser): Proxy address: 127.0.0.1, Allowed ports: 443,80,9150,9151,6969, then Restart it. Note: it doesnt makes you 100% invisible, as i said before, will depend entirely on your browser/config you have on it.

- Prefer a bridged connection: just in case you want to hide it from your ISP, or, even if Tor is not allowed in your country !!.
