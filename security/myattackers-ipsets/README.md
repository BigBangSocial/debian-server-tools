# Hostile networks

### Classifying Attackers

- 25% are known hostile networks (nothing good comes from them)
- 25% are bots
- 25% come from known cloud providers
- 25% are "researchers"

Source: https://www.hackerfactor.com/blog/index.php?/archives/775-Scans-and-Attacks.html

See also Access Watch database: https://access.watch/database

### Usage

Run `myattackers-install.sh`

### Usage on systems without ipset

```bash
grep -h '^add' *.ipset | cut -d " " -f 3 | sortip \
    | xargs -L 1 echo iptables -I myattackers -j REJECT -s
```
