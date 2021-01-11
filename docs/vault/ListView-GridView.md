---
id: f8df2222-90a2-4213-a103-bc329ef90a8c
title: ListView-GridView
desc: ''
updated: 1610379282098
created: 1610378131436
---

## ListView-GridView

```dart

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return Column(children: <Widget>[
    ListTile(title:Text("商品列表")),
    Expanded(
      child: ListView.builder(itemBuilder: (BuildContext context, int index) {
        return ListTile(title: Text("$index"));
      }),
    ),
  ]);
  }
}
```