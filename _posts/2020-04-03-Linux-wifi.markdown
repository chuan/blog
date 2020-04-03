---
layout: post
title: Set up Linux wifi one liner
---

```
# wpa_supplicant -B -i <interface> -c <(wpa_passphrase '<SSID>' '<password>')
# dhcpcd
```
