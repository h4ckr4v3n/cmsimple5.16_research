## Basic Info

- **Exploit Title:** CMSimple 5.16 Validate links SSRF
- **Exploit Author:** h4ckr4v3n
- **Vendor Homepage:** https://www.cmsimple.org/
- **Version:** 5.16
- **Tested on:** Ubuntu 22.04/PHP 7.4/Nginx 1.18.0

## Description
The validate links functionality allows an attacker to perform SSRF attacks

## Proof of Concept
1) Log in as Administrator
2) Go to Edit mode of any page
3) Insert link to Burp Collaborator in page editor
4) Get the request
5) You can check internal infrastructure. If there is an error it means that the target host is unreachable
