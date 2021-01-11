---
id: 8c48e3af-8ff9-49b9-b08a-67e08b8c80bf
title: Row-Column
desc: ''
updated: 1610377692345
created: 1610376929688
---

## Row-Column 主轴和纵轴

> 参考文档: https://book.flutterchina.club/chapter4/row_and_column.html

对于线性布局，有主轴和纵轴之分，如果布局是沿水平方向，那么主轴就是指水平方向，而纵轴即垂直方向；如果布局沿垂直方向，那么主轴就是指垂直方向，而纵轴就是水平方向。在线性布局中，有两个定义对齐方式的枚举类MainAxisAlignment和CrossAxisAlignment，分别代表主轴对齐和纵轴对齐。


```dart
Row(
  children: <Widget>[
    Expanded(
      child: Container(
        color: Colors.red,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 1,
    ),
    Expanded(
      child: Container(
        color: Colors.yellow,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 2,
    ),
    Expanded(
      child: Container(
        color: Colors.blue,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 1,
    ),
  ],
)
```
![](/assets/images/2021-01-11-23-00-07.png)

Column


Column可以在垂直方向排列其子组件。参数和Row一样，不同的是布局方向为垂直，主轴纵轴正好相反，读者可类比Row来理解

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Column(
  children: <Widget>[
    Expanded(
      child: Container(
        color: Colors.red,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 2,
    ),
    Expanded(
      child: Container(
        color: Colors.yellow,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 2,
    ),
    Expanded(
      child: Container(
        color: Colors.blue,
        padding: EdgeInsets.all(5.0),
      ),
      flex: 2,
    ),
  ],
)
    );
  }
}
```
![](/assets/images/2021-01-11-23-07-32.png)