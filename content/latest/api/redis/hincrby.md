---
title: HINCRBY
linkTitle: HINCRBY
description: HINCRBY
menu:
  latest:
    parent: api-redis
    weight: 2135
aliases:
  - api/redis/hincrby
  - api/yedis/hincrby
---

## SYNOPSIS
<b>`HINCRBY key field delta`</b><br>
This command adds `delta` to the number that is associated with the given field `field` for the hash `key`. The numeric value must a 64-bit signed integer.
<li>If the `key` does not exist, a new hash container is created. If the field `field` does not exist in the hash container, the associated string is set to "0".</li>
<li>If the given `key` is not associated with a hash type, or if the string  associated with `field` cannot be converted to an integer, an error is raised.</li>

## RETURN VALUE
Returns the value after addition.

## EXAMPLES
```{.sh .copy .separator-dollar}
$ HSET yugahash f1 5
```
```sh
1
```
```{.sh .copy .separator-dollar}
$ HINCRBY yugahash f1 3
```
```sh
8
```
```{.sh .copy .separator-dollar}
$ HINCRBY yugahash non-existent-f2 4
```
```sh
4
```
```{.sh .copy .separator-dollar}
$ HINCRBY non-existent-yugahash f1 3
```
```sh
3
```

## SEE ALSO
[`hexists`](../hexists/), [`hget`](../hget/), [`hgetall`](../hgetall/), [`hkeys`](../hkeys/), [`hlen`](../hlen/), [`hmget`](../hmget/), [`hmset`](../hmset/), [`hset`](../hset/), [`hincrby`](../hincrby/), [`hstrlen`](../hstrlen/), [`hvals`](../hvals/)