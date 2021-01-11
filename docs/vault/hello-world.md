---
id: 0429293c-6f3f-4324-84de-96ecf834b38e
title: Hello World
desc: ''
updated: 1610375163208
created: 1610371117428
---

# hello world

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Text('hello world'),
    );
  }
}
```
![](/assets/images/2021-01-11-22-25-56.png)