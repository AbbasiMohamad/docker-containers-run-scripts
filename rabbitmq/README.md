## run command

```console
docker run --hostname rabbitmq --name rabbitmq \
		 -p 5672:5672 -p 15672:15672 \
		 -e RABBITMQ_ERLANG_COOKIE='rabbitcookie' \
		 -d --restart=always \
		 --network host \ #if you want
		 rabbitmq:3.11.5-management
```

## example

```console
docker run --hostname rabbitmq --name rabbitmq \
		 -p 5672:5672 -p 15672:15672 \
		 -e RABBITMQ_ERLANG_COOKIE='rabbitcookie' \
		 -d --restart=always \
		 --network host \ #if you want
		 rabbitmq:3.11.5-management
```
