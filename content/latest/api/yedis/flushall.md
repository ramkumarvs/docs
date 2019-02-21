---
title: FLUSHALL
linkTitle: FLUSHALL
description: FLUSHALL
menu:
  latest:
    parent: api-redis
    weight: 2064
aliases:
  - /latest/api/redis/flushall
  - /latest/api/yedis/flushall
isTocNested: true
showAsideToc: true
---

## Synopsis
<b>`FLUSHALL`</b><br>
This command deletes all keys from all databases.

This functionality can be disabled by setting the yb-tserver gflag `yedis_enable_flush` to `false`.

## Return Value
Returns status string.

## Examples

```sh
$ SET yuga1 "America"
```

```
"OK"
```

```sh
$ SET yuga2 "Africa"
```

```
"OK"
```

```sh
$ GET yuga1
```

```
"America"
```

```sh
$ GET yuga2
```

```
"Africa"
```

```sh
$ FLUSHALL
```

```
"OK"
```

```sh
$ GET yuga1
```

```
(null)
```

```sh
$ GET yuga2
```

```
(null)
```

## See Also
[`del`](../del/), [`flushdb`](../flushdb/)