# Millionware (mw)

## Functions

### mw.register_callback
See [Callbacks](https://docs.millionware.vip/script_callbacks/).

---

### mw.time
Returns the date in the provided format. See [this page](https://www.cplusplus.com/reference/iomanip/put_time/) for parameters.

```mw.time(fmt: string):string```

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| fmt            | string        | The date format to return  |

```lua
print(mw.time("%c %Z"))
```

**Output: 05/10/21 09:13:45 Pacific Daylight Time**

---

### mw.unix_time
Returns the number of seconds since 00:00 hours, Jan 1, 1970 UTC (i.e., the current unix timestamp).

```mw.unix_time():number```

```lua
print(mw.unix_time())
```

**Output: 1620663342**

---
