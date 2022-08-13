# Redis

For better reference and _**time complexities**_ of different commands : [Official Docs](https://redis.io/commands/append/)

## Installation

```bash
curl -fsSL https://packages.redis.io/gpg | sudo gpg --dearmor -o /usr/share/keyrings/redis-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/redis-archive-keyring.gpg] https://packages.redis.io/deb $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/redis.list

sudo apt-get update
sudo apt-get install redis
```

## Start server
```bash
redis-server
```

## Start interactive mode
```bash
redis-cli
```

## Commands List

```bash
# Note that SET will replace any existing value already stored into the key, in the case that the key already exists, even if the key is associated with a non-string value. So SET performs an assignment.
set first_name miyamoto
```

```bash
# outputs miyamoto
get first_name
```

```bash
del first_name
```

```bash
# display all keys
keys *
```

```bash
# delete all keys
flushall
```

```bash
# display expiration time remaining of a key
# once expiration time expires, the key will be deleted
# stands for time to live
# ttl outputs either expiration-time or the following value
# -1 stands for infinite
# -2 stands for deleted
ttl first_name
```

```bash
# set ttl for an existing key
# ttl of 10 means expire in 10 seconds
ttl first_name 10
```

```bash
# set ttl while creating a key
# ttl of last_name is 10 seconds
setex last_name 10 mushashi
```

```bash
# return of 0 in the output means false, 1 is true
exists first_name
```

```bash
# get mykey outputs "hello world"
append mykey "Hello"
append mykey " world"
```


