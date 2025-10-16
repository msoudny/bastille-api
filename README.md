# bastille-api

API Interface for Bastille (https://bastillebsd.org/)


Commands
========

This API currently does the following commands:

create

destroy

start

stop

restart

rename


Setup
-----

Fist clone the repo then cd into bastille-api.  Now you uneed to initialize 
the go module.

```shell
go mod init bastille-api
go mod tidy
```

Now run the API on your server:
```sne..
go run .
```

You should see:
```shell
✅ BastilleBSD API running on http://localhost:8080
```

Now you are ready to run requests.  Here are some sample requests:
```shell
Create a jail
-------------
curl "http://localhost:8080/jails/create?name=testjail&release=14.2-RELEASE&ip=192.168.0.10&iface=em0"

Start jail
------------
curl "http://localhost:8080/jails/start?name=testjail"

Rename jail
-----------
curl "http://localhost:8080/jails/rename?old=testjail&new=myjail"

Restart jail
------------
curl "http://localhost:8080/jails/restart?name=myjail"

Stop jail
---------
curl "http://localhost:8080/jails/stop?name=myjail"

Destroy jail
------------
curl "http://localhost:8080/jails/destroy?name=myjail"
```


