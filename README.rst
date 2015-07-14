# ConfigCollector
This tool collects configuration file of multiple routers.

# Support router's OS
- IOS
- IOS-XE
- IOS-XR
- JUNOS

# Install
Download this tool.

```
$ git clone git@github.com:taijiji/ConfigCollector.git
```

Install python module using pip.

```
$ pip install -r requirements.txt
```

# How to use this tool

```
python configcollector.py -i [json file]
```

You can describe multipul routers using json format.
The router's OS is select from the below list.
- JUNOS
- IOS
- IOS-XE
- IOS-XR

This is sample json file.

```sample_routers.json
[
    {
        "hostname" : "router1",
        "username" : "user1",
        "password" : "aaabbbccc",
        "ipv4"     : "192.168.0.1",
        "os"       : "JUNOS"
    },
    {
        "hostname" : "router2",
        "username" : "user2",
        "password" : "aaabbbccc",
        "ipv4"     : "192.168.0.2",
        "os"       : "IOS-XR"
    },
    {
        "hostname" : "router3",
        "username" : "user3",
        "password" : "aaabbbccc",
        "ipv4"     : "192.168.0.3",
        "os"       : "IOS"
    }
]
```

After running this tool as default setting, the gotten router configuration is saved under "output" directory.

Example:

```
$ ls output
router1.txt  router2.txt  router3.txt
```

```
$ less  output/router1.txt

show configuration | no-more
## Last commit: 2015-05-01 17:00:00 JST by user1
version x.x.x;
system {
    host-name router1;
    time-zone Asia/Tokyo;
(snip)
```

# blog
Posted technical blog in Qiita (In Japanese).
http://qiita.com/taijijiji/items/620908c1bec27e1ea933