nmap -p 80,443 -sV -sC target.com

# Example output:
80/tcp  open  http     Microsoft IIS httpd 10.0
| http-server-header: Microsoft-IIS/10.0
|_http-title: Welcome to IIS

443/tcp open  ssl/http Microsoft IIS httpd 10.0

==================== Next Scan ====================

nmap -p 80,443 --script http-iis-short-name-brute target.com

# Example output:
| http-iis-short-name-brute:
|   VULNERABLE:
|   IIS Short Name (8.3) Enumeration
|   State: VULNERABLE
|   Discovered: /ASPNET~1/
|_  Discovered: /UPLOAD~1/

