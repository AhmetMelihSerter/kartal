# kartal

![kartal](https://www.gezilecekyerler.biz/wp-content/uploads/2015/12/Kartal-%C4%B0stanbul.jpg)

Kartal is the place for my borning country so I created an extension for giving born to more power with simple use.
If you want to example with these extensions, you should be look example folder.

------

## Future Extension

You can easy use for network or any future request.

```dart
  Future<String> fetchDummyData(BuildContext context) async {
    await Future.delayed(context.durationLow);
    return Future.value('Okey');
  }

  @override
  Widget build(BuildContext context) {
    return fetchDummyData(context).toBuild<String>(
        onSuccess: (data) {
          return Text(data);
        },
        loaindgWidget: CircularProgressIndicator(),
        notFoundWidget: Text('Oh no'),
        onError: FlutterLogo());
  }
```

## Context Extension

------
You can easy to use context power so context help for many needs.

### General Context Extension

I use the most this extesnion. It's  most needed for the your products.

```dart
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(brightness: context.appBrightness),
      body: Container(
        height: context.mediaQuery.size.height,
        color: context.colorScheme.onBackground,
        child: Text(context.isKeyBoardOpen ? 'Open' : 'Close', style: context.textTheme.subtitle1),
      ),
    );
  }
```

### Widget Extension

Sometimes need visible widget so you can this extension.

```dart
extension WidgetExtension on Widget {
  Widget toVisible(bool val) => val ? this : SizedBox(height: 1);
}

```

### MediaQuery Extension

These extension gives device size use so you can need dynamic(grid) value for device aspect, use the dyanmic height or width.

```dart
  SizedBox(
      height: context.dynamicHeight(0.1),
      width: context.dynamicWidth(0.1),
      child: Text('${context.lowValue}'),
    );
  }

```

### Navigation Extension

These directly access navigation features.

```dart
   Column(
        children: [
          FloatingActionButton(
            child: Text('Navigation Prop'),
            onPressed: () {
              context.navigation.canPop();
            },
          ),
          FloatingActionButton(
            onPressed: () {
              context.pop();
            },
            child: Text('Navigation Pop'),
          ),
          FloatingActionButton(
            onPressed: () {
              context.navigateName('/hello');
            },
            child: Text('Navigation Named'),
          ),
          FloatingActionButton(
            onPressed: () {
              context.navigateToReset('/hello');
            },
            child: Text('Navigation Named and Remove'),
          ),
        ],
      )
```

### Duration Extension

These extensions mainly for animation use.

```dart
AnimatedOpacity(
      opacity: context.isKeyBoardOpen ? 1 : 0,
      duration: context.durationLow,
      child: Text('${context.durationLow.inHours}'),
    );
```

### Padding Extension

These extensions declare project main padding values.

```dart
Padding(
      padding: context.paddingLow,
      child: Padding(
        padding: context.horizontalPaddingMedium,
        child: Text('${context.durationLow.inHours}'),
      ),
    )
```

### Empty Widget Extension

Sometimes need empty widget screen for space area, you can use that time.

```dart
Column(
      children: [
        Text('${context.durationLow.inHours}'),
        context.emptySizedHeightBoxHigh,
        Row(
          children: [Text('Row'), context.emptySizedWidthBoxLow, Text('Row')],
        )
      ],
    )
```

### Radius Extension

This extension only uses to draw the border.

```dart
  Container(
      decoration: BoxDecoration(borderRadius: context.lowBorderRadius),
    );

```

## Image Extension 🌠

------

You can use very easy rotiaton from image.

```dart
  @override
  Widget build(BuildContext context) {
    return Image.network('https://picsum.photos/200/300').bottomRotation;
  }
```

## Intager Extensıon

------
Now, we has a a little code.

```dart
extension IntagerExtension on int {
  int get randomValue => Random().nextInt(17);
}
```

## String Extension

------

Strıng need validation, color, launch, share etc.

### Validation Extension

Validate your string value to some features.

```dart
extension StringValidatorExtension on String {
  bool get isNullOrEmpty => this == null || this.isEmpty;
  bool get isNotNullOrNoEmpty => !isNullOrEmpty;

  bool get isValidEmail => RegExp(RegexConstans.instance.emailRegex).hasMatch(this);
}

```

### Input Formatter

You need the value mask and validation use formatter extension.

```dart
Column(
      children: [
        TextFormField(validator: (value) => value.isNotNullOrNoEmpty ? null : 'fail'),
        TextFormField(validator: (value) => value.isValidEmail ? null : 'fail'),
        TextField(
          inputFormatters: [InputFormatter.instance.phoneFormatter],
          onChanged: (value) {
            print('${value.phoneFormatValue}');
          },
        )
      ],
    );

```

### Launch Any Content In App Dialog Extension

You need open the value in device system. You can just say string value to launch prefix.

```dart
extension LaunchExtension on String {
  get launchEmail => launch("mailto:$this");
  get launchPhone => launch("tel:$this");
  get launchWebsite => launch("$this");
}
```

### Share Any Content External Apps Extension

These extension share your value to other apps or optional apps.

```dart

  void shareWhatssApp(String value) {
    value.shareWhatsApp();
  }

  void openWeb(String value) {
    value.launchWebsite;
  }
```

### Authorization Extension

Sometimes need this extension from send service request so easy create bearer token string.

```dart
  void bearerTokenHeader() {
    print('TOKEN-X-X-X'.beraer);
  }
```

## Tasks

------

- [ ] Advance String Extension
- [ ] More Integer Extension
- [ ] Unit Test
- [ ] File Extension
- [ ] SQLite etc. extension
- [ ] Application Extensions

------

## License

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

2020 created for @VB10

## Youtube Channel

[![Youtube](https://yt3.ggpht.com/a/AATXAJyul3hpzl86GIjF-EZxBzy6T62PJxpvzRwz9AbUOw=s288-c-k-c0xffffffff-no-rj-mo)](https://www.youtube.com/watch?v=UCdUaAKTLJrPZFStzEJnpQAg)