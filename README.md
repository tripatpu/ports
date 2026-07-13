# nmap
nmap -sV -p $(cat bugbounty-ports-clean.txt) target.com

# naabu
naabu -p $(cat bugbounty-ports-clean.txt) -host target.com

# nmap (one target per line in targets.txt)
nmap -sV -iL targets.txt -p $(cat bugbounty-ports-clean.txt)

# naabu
naabu -p $(cat bugbounty-ports-clean.txt) -list targets.txt

# naabu piped to nmap for service detection
naabu -p $(cat bugbounty-ports-clean.txt) -list targets.txt -silent | nmap -sV -iL -
