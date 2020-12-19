# Docker Autostart in WSL2

```
if [ ! -n "$CONTAINER_NAME" ]; then
	if [ -n "`service docker status | grep not`" ]; then
		sudo service docker start
	fi
fi
```
