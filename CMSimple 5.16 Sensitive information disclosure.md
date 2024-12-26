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
![cmsimple_disclosure1](https://github.com/user-attachments/assets/48e093cd-ccec-4a17-bb5b-0af1aa84b827)
![cmsimple_disclosure2](https://github.com/user-attachments/assets/978d6259-270f-4cea-b3d2-ad814d4d6b05)
![cmsimple_disclosure3](https://github.com/user-attachments/assets/3e7b8447-ca7c-4423-892d-d42b28466076)
![cmsimple_disclosure4](https://github.com/user-attachments/assets/de7aa67d-5ff7-478f-a567-5577c79b05de)
![cmsimple_disclosure5](https://github.com/user-attachments/assets/43c70afa-23d0-46cc-8baf-25a5d6a90d48)
![cmsimple_disclosure6](https://github.com/user-attachments/assets/a926c7ba-052b-41ee-8f1c-9f829402f91e)
