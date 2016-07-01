# mac_tz_jst_plist

Somehow, some rails application becomes very slow with Anti-Virus software on Mac OS X, because it access to "/etc/localtime"(link to "/usr/share/zoneinfo/Asia/Tokyo" for example) so often (like 100 times per sec).

To avoid to access the "/etc/localtime" file, we can explicitly set environment variable TZ like export TZ=JST-9 .

To do that, put the tz.plist file as ~/Library/LaunchAgents/tz.plist , and run command:

```
$ launchctl load ~/Library/LaunchAgents/tz.plist
```

Application started after the command will have environment variable TZ=JST-9 .


Ref:

[Setting environment variables via launchd.conf no longer works in OS X Yosemite/El Capitan?](http://stackoverflow.com/questions/25385934/setting-environment-variables-via-launchd-conf-no-longer-works-in-os-x-yosemite)

[HowTo: Set an Environment Variable in Mac OS X - launchd.plist](http://www.dowdandassociates.com/blog/content/howto-set-an-environment-variable-in-mac-os-x-launchd-plist/)


