---
title: "Module Details: sajoin (v3)"
---

## The "sajoin" Module

### Description

This module adds the `/SAJOIN` command which allows server operators to force users to join one or more channels.

### Configuration

To load this module use the following `<module>` tag:

```xml
<module name="sajoin">
```

#### `<class>`

This module extends the core `<class:privs>` key with the following values:

Name                | Description
------------------- | -----------
users/sajoin-others | Allows server operators to `/SAJOIN` users other than themselves.

#### Example Usage

Allows server operators with the class named BasicOper to `/SAJOIN` users other than themselves.

```xml
<class name="BasicOper"
       ...
       commands="... SAJOIN ..."
       privs="... users/sajoin-others ...">
```

### Commands

Name   | Parameter Count | Syntax                            | Description
------ | --------------- | --------------------------------- | -----------
SAJOIN | 1-2             | `[<nick>] <channel>[,<channel>]+` | Forces &lt;nick&gt; to join &lt;channel&gt;. If no nick is specified, forces the server operator issuing the command to join.

#### Example Usage

Forces Sadie to join #channel:

```plaintext
/SAJOIN Sadie #channel
```

Forces the server operator issuing the command to join #channel:

```plaintext
/SAJOIN #channel
```
