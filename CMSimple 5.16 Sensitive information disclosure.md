## Basic Info

- **Exploit Title:** CMSimple 5.16 Sensitive information disclosure
- **Exploit Author:** h4ckr4v3n
- **Vendor Homepage:** https://www.cmsimple.org/
- **Version:** 5.16
- **Tested on:** Ubuntu 22.04/PHP 7.4/Nginx 1.18.0

## Description
CMSimple 5.16 allows the user to read cms source code through manipulation of the file name in the file parameter of a GET request.

## Proof of Concept
1) Log in as Administrator.
2) In admin dashboard you can view and edit config, language, template or stylesheet
3) After clicking on edit one of these files you need to intercept outgoing request
4) Change `/?file=language&action=array` to `/?file=login&action=view`
5) Now you can read and even edit CMSimple source code such as login.php,adm.php,cms.php