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