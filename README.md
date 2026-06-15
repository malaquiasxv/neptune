# < --- [ TheOnionBox ] --- > #

[!] Bash based script that automates a secure Tor+Firewall+No IPv6 configuration on linux distros only, (uses Tor, nftables and the sysctl utility to talk directly to the linux kernel and ensure no leaks !!).


# [ About Boot ] #

[!] Supported service managers are: Open-RC, Systemd and Runit only, maybe i will add some more then, however automate it on boot is not that hard, will completely depend on your service manager.


# [ About Dependencies ] # 

[!] Required PKGs: 
- openbsd-netcat curl tor coreutils util-linux bash nftables sudo

# [ About Usage ] #

[!] Script content(inside TheOnionBox's dir):

- example_bridges.txt >> It is just a list of tor bridges, you can grab them from here: https://bridges.torproject.org/options/en, or, if you prefer .onion: kgclfuro65jjlivyzfmxiq2kyv5lickrl4qd.onion/options/en

- onionbox >> This is the main script, contains all the actions, from here you run "./onionbox start".

- osh >> An ultra simple/fast user-friendly shell that only speaks TheOnionBox params, ex: "start", "stop", "myip", etc.

- try-dot-onion >> Try to curl .onion addresses(this script comes ith some of them, for example: duckduckgo, hiddenwiki, etc) by running ./try-dot-onion, uses default's socks5 proxy address(127.0.0.1:9150), might fail if you use different one or if tor is not running.

[!] Script actions: 

--start, --stop, --restart, --boot-enable, --boot-disable, --myip, --changeid, --set-bridges --reset-config, --link, --show-config, --fast-shell.

- Run 'onionbox --help', for detailed info.

[!] To use it right now: 
- Note: always run this as root, (if sudo/git installed in your system)

- git clone https://github.com/0xmalaquias/TheOnionBox && cd TheOnionBox && chmod +x * && ./onionbox help

# [ Highly Recommended actions ] #

- Configure a Web Browser(prefer tor's one, it is very easy): You would have to force its internet connection to the socks5 proxy address/ports, ex(if torbrowser): Proxy address: 127.0.0.1, Allowed ports: 443,80,9150,9151,6969, then Restart it. Note: it doesnt makes you 100% invisible, as i said before, will depend entirely on your browser/config you have on it.

- Prefer a bridged connection: just in case you want to hide it from your ISP (because it is an obfuscated/encrypted connection designed for), or, even if Tor is not allowed in your country !!.
