# fijkplayer (Video player plugin for Flutter) Flutter 媒体播放器

**[手把手带你写 Flutter 系统音量插件](https://www.yuque.com/befovy/share/flutter_volume)**

[![pub package](https://img.shields.io/pub/v/fijkplayer.svg)](https://pub.dartlang.org/packages/fijkplayer) &nbsp; &nbsp;
[![Build Status](https://travis-ci.org/befovy/fijkplayer.svg?branch=master)](https://travis-ci.org/befovy/fijkplayer) &nbsp; &nbsp;

A Flutter media player plugin for iOS and android based on [ijkplayer](https://github.com/befovy/ijkplayer)

您的支持是我们开发的动力。 欢迎Star，欢迎PR~。
[Feedback welcome](https://github.com/befovy/fijkplayer/issues) and
[Pull Requests](https://github.com/befovy/fijkplayer/pulls) are most welcome!

## Documentation 文档

* Development Documentation https://fijkplayer.befovy.com/docs/en/ quick start、guide、and concepts about fijkplayer 
* 开发文档  https://fijkplayer.befovy.com/docs/zh/ 包含快速开始、使用指南、fijkplayer 中的概念理解
* dart api https://pub.dev/documentation/fijkplayer/ detail API and argument explaination
* Release Notes https://github.com/befovy/fijkplayer/releases and [CHANGELOG.md](./CHANGELOG.md)
* FAQ https://fijkplayer.befovy.com/docs/zh/faq.html

## Installation 安装

Add `fijkplayer` as a [dependency in your pubspec.yaml file](https://flutter.io/using-packages/). 

```yaml
dependencies:
  fijkplayer: ^0.2.3
```

Use git branch which not published to pub.
```yaml
dependencies:
  fijkplayer:
    git:
      url: https://github.com/befovy/fijkplayer.git
      ref: develop # can be replaced to branch or tag name
```

## Example 示例

```dart
import 'package:fijkplayer/fijkplayer.dart';
import 'package:flutter/material.dart';

class VideoScreen extends StatefulWidget {
  final String url;

  VideoScreen({@required this.url});

  @override
  _VideoScreenState createState() => _VideoScreenState();
}

class _VideoScreenState extends State<VideoScreen> {
  final FijkPlayer player = FijkPlayer();

  _VideoScreenState();

  @override
  void initState() {
    super.initState();
    player.setDataSource(widget.url, autoPlay: true);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(title: Text("Fijkplayer Example")),
        body: Container(
          alignment: Alignment.center,
          child: FijkView(
            player: player,
          ),
        ));
  }

  @override
  void dispose() {
    super.dispose();
    player.release();
  }
}

```

## Already in use in following apps
Contact me or create pull request to add your app here.

## Contributors 贡献者 ✨

Thanks goes to [these wonderful people](./CONTRIBUTORS.md) ([emoji key](https://allcontributors.org/docs/en/emoji-key))

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome

## iOS Warning 警告

Warning: The fijkplayer video player plugin is not functional on iOS simulators. An iOS device must be used during development/testing. For more details, please refer to this [issue](https://github.com/flutter/flutter/issues/14647).


## Next Plan 计划

See the development plan of next version in https://github.com/befovy/fijkplayer/projects/2
