# Passive tools

subfinder -d example.com -all -silent -o subfinder.txt
assetfinder --subs-only example.com > assetfinder.txt
amass enum -passive -d example.com -o amass_passive.txt
findomain -t example.com -u findomain.txt
chaos -d example.com > chaos.txt
waybackurls example.com | unfurl -u domains > wayback.txt

# Active tools

amass enum -active -d example.com -o amass_active.txt
dnsx -d example.com -resp -o dnsx.txt
puredns bruteforce wordlist.txt example.com -o puredns.txt

# Combine all results

cat *.txt | sort -u > all_subdomains.txt




cat all_subdomains.txt | httpx-toolkit -mc 200 -sc -td -title -server | grep IIS




cat all_subdomains.txt | httpx-toolkit -mc 200 -sc -td -title -server | grep -i "IIS/7.5"
cat all_subdomains.txt | httpx-toolkit -mc 200 -sc -td -title -server | grep -i "IIS/8.5"
cat all_subdomains.txt | httpx-toolkit -mc 200 -sc -td -title -server | grep -i "IIS/10.0"



cat all_subdomains.txt | nuclei -t /nuclei-templates/http/misconfiguration/iis-shortname-detect.yaml
cat all_subdomains.txt | nuclei -tags iis
