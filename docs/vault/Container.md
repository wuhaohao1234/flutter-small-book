---
id: 2fa0136c-3af2-43e5-b6f6-57a1628998c3
title: Container
desc: ''
updated: 1610376814514
created: 1610376084040
---

## Container
Container在Flutter中太常见了。官方给出的简介，是一个结合了绘制（painting）、定位（positioning）以及尺寸（sizing）widget的widget。

可以得出几个信息，它是一个组合的widget，内部有绘制widget、定位widget、尺寸widget。后续看到的不少widget，都是通过一些更基础的widget组合而成的。

### 组成
Container的组成如下：

最里层的是child元素；
child元素首先会被padding包着；
然后添加额外的constraints限制；
最后添加margin。
Container的绘制的过程如下：

首先会绘制transform效果；
接着绘制decoration；
然后绘制child；
最后绘制foregroundDecoration。
Container自身尺寸的调节分两种情况：

Container在没有子节点（children）的时候，会试图去变得足够大。除非constraints是unbounded限制，在这种情况下，Container会试图去变得足够小。
带子节点的Container，会根据子节点尺寸调节自身尺寸，但是Container构造器中如果包含了width、height以及constraints，则会按照构造器中的参数来进行尺寸的调节。
### 布局行为
由于Container组合了一系列的widget，这些widget都有自己的布局行为，因此Container的布局行为有时候是比较复杂的。

一般情况下，Container会遵循如下顺序去尝试布局：

对齐（alignment）；
调节自身尺寸适合子节点；
采用width、height以及constraints布局；
扩展自身去适应父节点；
调节自身到足够小。
进一步说：

如果没有子节点、没有设置width、height以及constraints，并且父节点没有设置unbounded的限制，Container会将自身调整到足够小。
如果没有子节点、对齐方式（alignment），但是提供了width、height或者constraints，那么Container会根据自身以及父节点的限制，将自身调节到足够小。
如果没有子节点、width、height、constraints以及alignment，但是父节点提供了bounded限制，那么Container会按照父节点的限制，将自身调整到足够大。
如果有alignment，父节点提供了unbounded限制，那么Container将会调节自身尺寸来包住child；
如果有alignment，并且父节点提供了bounded限制，那么Container会将自身调整的足够大（在父节点的范围内），然后将child根据alignment调整位置；
含有child，但是没有width、height、constraints以及alignment，Container会将父节点的constraints传递给child，并且根据child调整自身。
另外，margin以及padding属性也会影响到布局。


```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Center(
        child: Container(
          margin: const EdgeInsets.all(10.0),
          color: Colors.amber[600],
          width: 48.0,
          height: 48.0,
          ),
      ),
    );
  }
}
```
![](/assets/images/2021-01-11-22-45-00.png)