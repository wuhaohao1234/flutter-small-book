---
id: fa9322f3-04ba-4baf-b0c8-878a63089710
title: Tabbar
desc: ''
updated: 1610502881319
created: 1610502831658
---

## tabbar

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    title: "TabBarWidget",
    home: MyApp(),
  ));
}


class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}


class _MyAppState extends State<MyApp> with SingleTickerProviderStateMixin{
  TabController _tabController;

  @override
  void initState() {
    super.initState();
    _tabController = TabController(vsync: this,length: 6);
  }

  @override
  void dispose() {
    _tabController.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("顶部Tab切换"),
        bottom: TabBar(
          tabs: <Widget>[
            Tab(text: "热门"),
            Tab(text: "推荐"),
            Tab(text: "关注"),
            Tab(text: "收藏"),
            Tab(text: "新增"),
            Tab(text: "点赞"),
          ],
          controller: _tabController,  // 记得要带上tabController
        ),
      ),
      body: TabBarView(
        controller: _tabController,
        children: <Widget>[
          Center(
              child: Text("这是热门的内容")
          ),
          Center(
              child: Text("这是推荐的内容")
          ),
          Center(
              child: Text("这是关注的内容")
          ),
          Center(
              child: Text("这是收藏的内容")
          ),
          Center(
              child: Text("这是新增的内容")
          ),
          Center(
              child: Text("这是点赞的内容")
          )
        ],
      ),
    );
  }
}
```
![](/assets/images/2021-01-13-09-54-37.png)