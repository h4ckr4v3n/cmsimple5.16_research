## Basic Info

- **Exploit Title:** CMSimple 5.16 Broken Access Control to log.php
- **Exploit Author:** h4ckr4v3n
- **Vendor Homepage:** https://www.cmsimple.org/
- **Version:** 5.16
- **Tested on:** Ubuntu 22.04/PHP 7.4/Nginx 1.18.0

## Description
CMSimple 5.16 allows the user to edit log.php file via print page.

## Proof of Concept
1) Log in as Administrator
2) Switch to the Settings>Log
3) Change url `/?file=log&action=view` to `/?file=log&action=edit`. You will get an error message
4) To bypass edit restriction go to url `/?&print&file=log`
5) You can edit log.php file to inject arbitrary php code
![cmsimple_logedit1](https://github.com/user-attachments/assets/6f5fd08f-95a2-44ce-b94c-c408db7af54c)
![cmsimple_logedit2](https://github.com/user-attachments/assets/5beec308-6104-4c76-b8aa-cc030fe3fc91)
![cmsimple_logedit4](https://github.com/user-attachments/assets/7ec57fe3-b856-4cf5-839b-63aa81814ee5)
![cmsimple_logedit5](https://github.com/user-attachments/assets/6c287561-2490-4d8f-9d37-61ac5b045599)
