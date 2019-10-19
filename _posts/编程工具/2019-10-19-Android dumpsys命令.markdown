---
layout: post
# title:  "Android dumpsys"
date:   2019-10-19 13:11:52 +0800
# categories: jekyll update
published: true
---

## dumpsys -l：查看所有可用服务，最常用到 dumpsys activity。
## dumpsys activity -h：查看activity服务的用法。
[-a] [-c] [-p PACKAGE] [-h] [WHAT]
- -a：输出服务端状态。
- -c：输出客户端状态。
- -p：指定包名。
- -h：查看帮助，即 dumpsys activity -h。
WHAT：
- a[ctivities]: activity stack state
- <font color=red>r[recents]: recent activities state</font>
- b[roadcasts] [PACKAGE_NAME] [history [-s]]: broadcast state
- broadcast-stats [PACKAGE_NAME]: aggregated broadcast statistics
- i[ntents] [PACKAGE_NAME]: pending intent state
- p[rocesses] [PACKAGE_NAME]: process state
- o[om]: out of memory management
- perm[issions]: URI permission grant state
- prov[iders] [COMP_SPEC ...]: content provider state
- provider [COMP_SPEC]: provider client-side state
- s[ervices] [COMP_SPEC ...]: service state
- as[sociations]: tracked app associations
- settings: currently applied config settings
- service [COMP_SPEC]: service client-side state
- package [PACKAGE_NAME]: all state related to given package
- all: dump all activities
- top: dump the top activity
## 查看app的activity栈
- `adb shell dumpsys activity -p [PACKAGE_NAME] r | grep Activities`