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
![cmsimple_ssrf1](https://github.com/user-attachments/assets/ea83c5d5-e6e8-4aa2-bbf5-5016cf4e88a8)
![cmsimple_ssrf2](https://github.com/user-attachments/assets/3efac26f-9b24-452f-b590-a5ae2db1fd99)
![cmsimple_ssrf3](https://github.com/user-attachments/assets/7381dd58-1585-4e80-a3de-0fcf1aa529f2)
![cmsimple_ssrf5](https://github.com/user-attachments/assets/ae7cacd9-6be0-4b31-95b4-68587f45c9c5)
