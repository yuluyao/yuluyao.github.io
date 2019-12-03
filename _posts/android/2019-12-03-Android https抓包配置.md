---
layout: post
category: Android 被忽略的知识
---



### Manifest添加配置文件

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest ... >
    <application android:networkSecurityConfig="@xml/network_security_config"
                    ... >
        ...
    </application>
</manifest>
```

### 配置文件的格式
```xml
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <base-config>
        <trust-anchors>
            <certificates src="..."/>
            ...
        </trust-anchors>
    </base-config>
    <domain-config>
        <domain>android.com</domain>
        ...
        <trust-anchors>
            <certificates src="..."/>
            ...
        </trust-anchors>
        <pin-set>
            <pin digest="...">...</pin>
            ...
        </pin-set>
    </domain-config>
    ...
    <debug-overrides>
        <trust-anchors>
            <certificates src="..."/>
            ...
        </trust-anchors>
    </debug-overrides>
</network-security-config>
```

### 典型的配置

```xml
<?xml version="1.0" encoding="utf-8"?>
<network-security-config>
    <!-- 仅调试模式下 -->
    <debug-overrides>
        <trust-anchors>
            <!-- 信任系统预装的CA证书 -->
            <certificates
              overridePins="true"
              src="system" />
            <!-- 信任用户添加的CA证书 -->
            <certificates
              overridePins="true"
              src="user" />
        </trust-anchors>
    </debug-overrides>
</network-security-config>
```

### 官方文档
> https://developer.android.com/training/articles/security-config.html