# mac_tz_jst_plist

Somehow, some rails application becomes very slow with Anti-Virus software on Mac OS X, because it access to "/etc/localtime"(link to "/usr/share/zoneinfo/Asia/Tokyo" for example) so often (like 100 times per sec).

To avoid to access the "/etc/localtime" file, we can explicitly set environment variable TZ like export TZ=JST-9 .

To do that, put the tz.plist file as ~/Library/LaunchAgents/tz.plist , and run command:

```
$ launchctl load ~/Library/LaunchAgents/tz.plist
```

Application started after the command will have environment variable TZ=JST-9 .

