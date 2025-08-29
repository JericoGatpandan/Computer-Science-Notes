![[Pasted image 20250820232912.png]]
https://askubuntu.com/questions/773446/unable-to-connect-via-mysql-workbench-to-localhost-in-ubuntu-16-04-passwordless

sudo systemctl start mysql
>username: root
>password: password

```
CREATE USER 'admin'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
```