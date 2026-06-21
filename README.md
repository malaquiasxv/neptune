# <[ ArchNoN Anonimation Tool v3.0.4 ]> #
- [notice] Bash based Tool that uses Tor's strongest privacy configuration, plus no IPv6 policy and a secure nftables firewall for linux distros.

- [warn] ArchNoN is a personal project developed by newmasterone27@gmail.com, if you will use it you have to know that developer wont answer in case of any issue occurs in your machine(perhaps, issues are not common, in fact, they are incredible weird).

- [warn] If you'll use it on a fakeroot/chroot env like proot/nethunter, on termux, you have to know that script will block you entirelly to use curl normally, (because it wont be able to apply firewall, only if you are rooted), to resolv any link you must use tool’s "link" param, or give to curl the param: --socks5-hostname 127.0.0.1:9150.


# [ Requeriments ] # 
- [warn] Required PKGs: (bash, if not installed), all other pkgs can be managed by tool, actually.
- [warn] Extra: Real full root access(to apply firewall rules and curl links normally as before, i mean, without needing the flag '--socks5-hostname 127.0.0.1:9150')


# [ Content ] #
- archnon >> Modern version of the script, it uses the modern, clean, faster alternative to iptables: nftables. Sometimes is much faster than old iptables(better on all sense).

- example_bridges.txt >> It is just a list of tor bridges, you can grab them from here: https://bridges.torproject.org/options/en, or, if you prefer .onion: kgclfuro65jjlivyzfmxiq2kyv5lickrl4qd.onion/options/en

- try-dot-onion >> Try to curl .onion addresses(this script comes with some of them, for example: duckduckgo, hiddenwiki, etc) by running ./try-dot-onion, uses default's socks5 proxy address(127.0.0.1:9150), it might fail if you use a different address/tor is not running.

- make_it_work >> ./make_it_work, just moves the shell, scripts to your /usr/bin dir(run as root).


# [ Script Params/Actions ] #

- [warn] usage: archnon <action>.

- start --> Start ArchNoN and Apply Firewall rules.

- stop --> Stop ArchNoN and Flush Firewall rules.

- restart--> Restart ArchNoN.

- boot-enable --> Enable ArchNoN on boot.

- boot-disable --> Disable ArchNoN on boot.

- myip --> Show Public IP Address.

- changeid --> Change Tor Public IP Address.

- bridges --> Load a custom Tor bridges configuration file, usage: archnon bridges <file> <kind> <binary>.

- config-reset --> Reset Tor's configuration file (/etc/tor/torrc) to ArchNoN's default.

- config-show --> Show configuration files that were touched by ArchNoN (/etc/tor/torrc, /etc/resolv.conf).

- config-load --> Load a custom Torrc(that is the file tor reads before start), usage: sudo archnon config-load <file>. 

- resolv --> Resolves .onion addresses.

- help --> Print this usage page.


# [ Clone ] #
- [warn] Run as root: git clone https://github.com/0xmalaquias/ArchNoN && cd ArchNoN && chmod +x * && ./make_it_work


# [ Boot ] #
- [notice] Supported service managers are: Open-RC, Systemd and Runit only.
- [warn] example: script detects if you use commands as: rc-service, rc-update, systemctl, sv, runit.

# [ Recommended ] #

- [notice] Configure a Web Browser(prefer tor's one, it is very easy): You would have to force its internet connection to the socks5 proxy address/ports, ex(if torbrowser): Proxy address: 127.0.0.1, Allowed ports: 443,80,9150,9151,6969, then Restart it. Note: it doesnt makes you 100% invisible, as i said before, will depend entirely on your browser/config you have on it.

- [notice] Prefer use Tor bridges: just in case you want to hide it from your ISP, Tor is not allowed in your country, or, you want to keep an encrypted much faster connection.
