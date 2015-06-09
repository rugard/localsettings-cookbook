localsettings Cookbook
======================

This is a wrapper cookbook for customize local settings of node.

Usage
-----
#### localsettings::default

Default setup is:

* Setup timezone to Europa/Moscow
* Setup ntp server as ntp-client (ntpdate-debian is not working after this cookbook is applyed) with server from default ntp pool list:

```
0.pool.ntp.org 1.pool.ntp.org 2.pool.ntp.org 3.pool.ntp.org
```

If you want setup additional local ntp servers (it has been already configured on you network) add attribute `ntp['peers']` in node role.

Just include `localsettings` in your node's `run_list`:

```json
{
  "name":"my_node",
  "run_list": [
    "recipe[localsettings]"
  ]
}
```

License and Authors
-------------------
Authors: 

skubriev@cvisionlab.com, Vladimir Skubriev
