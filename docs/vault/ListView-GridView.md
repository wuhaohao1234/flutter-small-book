---
id: f8df2222-90a2-4213-a103-bc329ef90a8c
title: ListView-GridView
desc: ''
updated: 1610466151853
created: 1610378131436
---

## ListView-GridView

### ListView

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: MyStatelessWidget()
    );
  }
}

class MyStatelessWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context){
    //Scaffold provide functionality of appbar, body of app etc
    return new Scaffold(
      appBar: new AppBar(title: new Text("Stateless Widget")),
      body: ListView(
          children: <Widget>[
            ListTile(
              leading: Icon(Icons.map),
              title: Text('Map'),
              subtitle: Text('Map'),
            ),
            ListTile(
              leading: Icon(Icons.mail),
              title: Text('Mail'),
              subtitle: Text('Mail'),
            ),
            ListTile(
              leading: Icon(Icons.message),
              title: Text('Message'),
              subtitle: Text('Message'),
            ),
          ],
        )
    );
  }
}
```
![](/assets/images/2021-01-12-23-39-26.png)

### GridView

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(home: MyStatelessWidget());
  }
}

class MyStatelessWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    //Scaffold provide functionality of appbar, body of app etc
    return new Scaffold(
      appBar: new AppBar(title: new Text("Stateless Widget")),
      body: GridView(
          gridDelegate: SliverGridDelegateWithFixedCrossAxisCount(
              crossAxisCount: 3, //横轴三个子widget
              childAspectRatio: 1.0 //宽高比为1时，子widget
              ),
          children: <Widget>[
            Icon(Icons.ac_unit),
            Icon(Icons.airport_shuttle),
            Icon(Icons.all_inclusive),
            Icon(Icons.beach_access),
            Icon(Icons.cake),
            Icon(Icons.free_breakfast)
          ]));
  }
}

```
![](/assets/images/2021-01-12-23-42-23.png)