# redis

[Redis quick start documentation](https://redis.io/topics/quickstart)

- `./deploy/install_local.step5.install_redis.sh` install and have it running
- check connection `redis-cli`
- check if Redis is working `redis-cli ping`
- if not connected, after installing `redis`, start the redis server with `redis-server`


- `GET <key>` get value of the key
- `DEL <key1> <key2> <key3> ...` remove the specified key(s)
  - return value is an integer reply (the number of keys that were removed)
- `KEYS '*'` get all keys

- save query output to a file `redis-cli GET <key> <dir>`
  - `redis-cli GET search_results__VSR0009866_f1a64a99936eb356dbb__xpos > /Users/zhuang/previous_search_results.txt`
