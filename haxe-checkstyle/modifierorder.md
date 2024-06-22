---
title: Modifier Order
toc: false
---

Checks that the order of modifiers conforms to the standards.

### Configuration

```json
{
    "type": "ModifierOrder",
    "props": {
        "severity": "WARNING",
        "modifiers": [
            "MACRO",
            "OVERRIDE",
            "PUBLIC_PRIVATE",
            "STATIC",
            "INLINE",
            "DYNAMIC",
            "FINAL"
        ]
    }
}
```

### Valid

```java
public static inline var COUNT:Int = 1;
```

```java
override public function close() {}
```

### Invalid

```java
inline public static var COUNT:Int = 1;
```

{{site.data.alerts.error}} modifier order for field "COUNT" is "inline public static" but should be "public static inline" {{site.data.alerts.end}}

```java
public override function close() {}
```

{{site.data.alerts.error}} modifier order for field "close" is "public override" but should be "override public" {{site.data.alerts.end}}
