---
layout: post
category: Swift语言
---

# Constants and Variables

## 定义常量与变量

常量与变量在使用之前必须先声明，声明常量使用`let`，声明变量使用`var`：
```swift
let maximumNumberOfLoginAttempts = 10
var currentLoginAttempt = 0
```

可以在一行内声明多个常量或变量：
```swift
var x = 0.0, y = 0.0, z = 0.0
```

## 类型声明

可以在定义常量或变量时，声明类型：
```swift
var welcomeMessage: String
```

在一行内声明多个常量或变量的类型：
```swift
var red, green, blue: Double
```

## 命名

常量或变量命名，不能以数字或特殊字符开头，不能包含空格，但可以使用Unicode字符：
```swift
let π = 3.14159
let 你好 = "你好世界"
let 🐶🐮 = "dogcow"
```


# Comments

单行注释：
```swift
// This is a comment.
```

多行注释：
```swift
/* This is also a comment
but is written over multiple lines. */
```

多行注释嵌套：
```swift
/* This is the start of the first multiline comment.
 /* This is the second, nested multiline comment. */
This is the end of the first multiline comment. */
```


# Semicolons

Swift不要求在每个语句后面加分号，但是一行内有多个语句时，要用分号隔开：
```swift
let cat = "🐱"; print(cat)
// Prints "🐱"
```


# Integers

## 整数边界

获取边界：
```swift
let minValue = UInt8.min  // minValue is equal to 0, and is of type UInt8
let maxValue = UInt8.max  // maxValue is equal to 255, and is of type UInt8
```

## Int

- On a 32-bit platform, Int is the same size as Int32.
- On a 64-bit platform, Int is the same size as Int64.

## UInt

- On a 32-bit platform, UInt is the same size as UInt32.
- On a 64-bit platform, UInt is the same size as UInt64.

# Floating-Point Numbers

`Double`和`Float`：
- Double represents a 64-bit floating-point number.
- Float represents a 32-bit floating-point number.

# Type Safety and Type Inference

带小数点的常数，会被判断为`Double`类型：
```swift
let pi = 3.14159
// pi is inferred to be of type Double
```


# Numeric Literals

整数有4种表示方式：
- 十进制数，没有前缀
- 二进制数，前缀为`0b`
- 八进制数，前缀为`0o`
- 十六进制数，前缀为`0x`
用4种方式表示17：
```swift
let decimalInteger = 17
let binaryInteger = 0b10001       // 17 in binary notation
let octalInteger = 0o21           // 17 in octal notation
let hexadecimalInteger = 0x11     // 17 in hexadecimal notation
```


浮点数可以用10进制或16进制表示，小数点两必须都有数字，并且：
1. 10进制浮点数，可以有指数部分，用大写或小写的e表示；
2. 16进制浮点数，**必须**有指数部分，用大写或小写的p表示。

举例：
- 1.25e2 表示 1.25 x 102，即 125.0。
- 1.25e-2 表示 1.25 x 10-2，即 0.0125。
- 0xFp2 表示 15 x 22，即 60.0。
- 0xFp-2 表示 15 x 2-2，即 3.75。

```swift
let decimalDouble = 12.1875
let exponentDouble = 1.21875e1
let hexadecimalDouble = 0xC.3p0
```

表示数字可以在前面加0，或中间加下划线：
```swift
let paddedDouble = 000123.456
let oneMillion = 1_000_000
let justOverOneMillion = 1_000_000.000_000_1
```

# Numeric Type Conversion


# Type Aliases


# Booleans



# Tuples


# Optionals


# Error Handling


# Assetions and Precoditions