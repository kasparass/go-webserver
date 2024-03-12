#### MYSQL Docker container

Created new user using command:

```shell
mysql>  CREATE USER 'web'@'%';
```

instead of

```shell
mysql>  CREATE USER 'web'@'localhost';
```

to be able to connect from outside of container.