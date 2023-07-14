
# Flutter-Dev-Discord-Tips-Tricks.

---

---

#### Q NestedScrollView

https://api.flutter.dev/flutter/widgets/NestedScrollView-class.html

---

#### Q Why not to use list view with shrink wrap 

https://www.youtube.com/watch?v=LUqDNnv_dh0

https://dartpad.dev/workshops.html?webserver=https://fdr-shrinkwrap-slivers.web.app#Step1

---

#### Q Local Image provider

https://pub.dev/packages/local_image_provider

---

#### Q Use of context after asynchronus gap.

Update :- with the new flutter version the mounted getter is added to build context itself. Now you can use context.mounted ...check if widgget is mounted if it is do the required operation. use in the did change dependancies.

---

#### Q Column and unbounded height of children 

It’s hidden in the docs
When a Column lays out its non-flex children (those that have neither Expanded or Flexible around them), it gives them **unbounded constraints** so that they can determine their own dimensions

---

#### Q Bi Directional List view

https://pub.dev/packages/bidirectional_listview

---

#### Q  Change Location of floting action button.

https://api.flutter.dev/flutter/material/FloatingActionButtonLocation-class.html


---

#### Q 
![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/ee26705c-07de-4941-b450-95955eacfe9e)

TextStyle(decoration: TextDecoration.lineThrough)

---

#### Q Svg to custom path in flutter.

​https://pub.dev/packages/path_drawing

---

#### Q For all kind of sensors battery 

https://plus.fluttercommunity.dev/

---

#### Q MediaQuery.sizeOf(context)

Note that it talks about using MediaQuery.of, which is not recommended.  There are new extensions on MediaQuery you can use, things like MediaQuery.sizeOf(context) which are better to use.  You should definitely check out the "other resources" section for a lot more info.

---
#### Q Lots of animation-based-on-scroll-position.those are pretty straightforward.

https://pub.dev/packages/flutter_animate
Container().animate(adaptor: ScrollAdaptor( ...)).zoomIn() 

---

#### Q source for free icons .

For the free and open source one, I was using https://feathericons.com/

---
#### Q All kind of font related changes.
![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/1e067410-3ef9-4660-aef1-c31aa420e578)


Tip- https://api.flutter.dev/flutter/painting/StrutStyle-class.html


---
#### Q Flutter state restoration like textfields. toggle buttons, bools. when we switch between the apps.

https://www.youtube.com/watch?v=5-u5VjPJsNI

---
#### Q Setstate called after the widget dispose. error.

https://www.youtube.com/watch?v=ZwDEHhD00c8. 

```bash
 void initState() {
    // TODO: implement initState
    if(mounted){
    super.initState();
    }
}
```

---

#### Q How to keep widgets alive even if we pop and push in the navigatior.

```bash
class KeepAliveWrapper extends StatefulWidget { 
   final Widget child; 
  
   const KeepAliveWrapper({super.key, required this.child}); 
  
   @override 
   KeepAliveWrapperState createState() => KeepAliveWrapperState(); 
 } 
  
 class KeepAliveWrapperState extends State<KeepAliveWrapper> 
     with AutomaticKeepAliveClientMixin<KeepAliveWrapper> { 
   @override 
   bool get wantKeepAlive => true; 
  
   @override 
   Widget build(BuildContext context) { 
     super.build(context); 
  
     return widget.child; 
   } 
 }
 ```

---

#### Q Dropdown for extra customisation.
https://pub.dev/packages/dropdown_button2

---

#### Q Deep link

https://docs.flutter.dev/ui/navigation/deep-linking

---

#### Q  Have no local changes you want to preserve you can reset to the remote state in git.
git reset --hard origin/<your_desired_branch>

---
#### Q how to use dart code/hive in web.
​https://pub.dev/packages/js

---

#### Q how to use dart code/hive in web.
​https://pub.dev/packages/js

---

#### Q How to restore state when we close app and reopen 

https://docs.flutter.dev/platform-integration/android/restore-state-android

---

#### Q How to create tutorial like effect(highlight Buttom or element with tooltip to explain what it is and a next button to show next step).

​(link)https://pub.dev/packages/showcaseview
(super_tooltip package)
(Compositedtransformfollower class)

---
#### Q What limitation exist in parallelism of flutter web appas? can we run dart code concurrently? i havent found good documentation or example.

wab uses javascript. but you can use this package.
Link(​https://pub.dev/packages/isolated_worker)

---

#### Yeah, unbounded text tries to stay in one line, spilling right over the edge Expanded provides a bounds.

---

#### Q How to hide or show more text within certain length.
Link(https://stackoverflow.com/questions/49572747/flutter-how-to-hide-or-show-more-text-within-certain-length)

---

#### Q How to remove Scroll Glow..

![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/d523829a-32eb-4ffc-8723-7195590defb6)

https://www.flutterclutter.dev/flutter/troubleshooting/2023-03-26-how-to-remove-scroll-glow/

---

#### How do you retry failed requests? 

```bash
while(!timeout){
  repeatUntilSuccess();
}
other
while (true) if (success()) break;

```
---

#### How to get This

![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/bb66c232-3f77-40f0-82ab-a226ae15169e)
https://api.flutter.dev/flutter/material/showModalBottomSheet.html

---
#### How to make this 

![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/4eb1c966-a8dd-4e49-8503-8d43c4fa98dc)

I did this recently for a walk through overlay.
You can use a custom clipper to punch a hole in the blur box.
You likely wont notice a performance difference
Punching a hole in the widget using a clipper will be easier because you can pass it any random rect

---

#### Shaders For the Text to show grediant.

There is one already IIRC
You can also use a simple shader:
```bash
final Shader linearGradient = LinearGradient(
  colors: <Color>[Color(0xffDA44bb), Color(0xff8921aa)],
).createShader(Rect.fromLTWH(0.0, 0.0, 200.0, 70.0));
Then apply to text:

Text(
        'Hello Gradients!',
        style: new TextStyle(
            fontSize: 60.0,
            fontWeight: FontWeight.bold,
            foreground: Paint()..shader = linearGradient),
      )
But there is a package as well $[simple_gradient_text]
FlutterDoc
BOT
 — Today at 2:03 AM
https://pub.dev/packages/simple_gradient_text
Dart packages
simple_gradient_text | Flutter Package
Create fast and simple gradient texts, whether linear or radial, you just decide the colors and the text to display, very easy.
```
  
 ---  
  
#### There's a widget that autosizes text to fit it's space, might want to look at that. ![AutoSizeText]

https://pub.dev/packages/auto_size_text

---

.contain is a property of BoxFit. ResizeImagePolicy is something else.
It turns out the issue was with CachedNetworkImageProvider. NetworkImage works as expected.
![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/048895d5-8dbc-4b02-b05e-bb659aeca3ab)
![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/cf2ff6bf-670e-4e53-bca9-35e951bf6a87)


---

#### Animated Sidebar

```bash
class _SamplePageState extends State<SamplePage> with SingleTickerProviderStateMixin {
  late final AnimationController _controller = AnimationController(
    duration: const Duration(seconds: 2),
    vsync: this,
  );

  late final Animation<Offset> _offsetAnimation = Tween<Offset>(
    begin: Offset.zero,
    end: const Offset(-3.0, 0.0),
  ).animate(CurvedAnimation(
    parent: _controller,
    curve: Curves.easeInOut,
  ));

  @override
  void dispose() {
    _controller.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Row(
      children: [
        SlideTransition(
          position: _offsetAnimation,
          child: const Padding(
            padding: EdgeInsets.all(8.0),
            child: FlutterLogo(size: 150.0),
          ),
        ),
        Placeholder(
            child: TextButton(
          child: const Text('press'),
          onPressed: () => _controller.forward(),
        )),
      ],
    );
  }
}
```
---

There's two... visibility is ones
the other is opacity or something
one of them keeps the widget's space in play, the other removes it entirely from the tree
Opacity works by making it transparent.  visibility works by removing it from the widget tree
Visibiiity looks like the more encompassing... you can flip settings to act like opacity

---

#### How to remove this.

![image](https://github.com/deeprajsinghsisodiya/Flutter-Dev-Discord-Tips-Tricks./assets/122676491/73e4bed7-885b-4909-8921-763ac82b29ce)

Tip : Use ![Scaffold.extendBody] to let the content sit under the bottom nav. Then add padding to the bottom of the content so it can scroll into view. 

https://api.flutter.dev/flutter/material/Scaffold/extendBody.html


---

#### Here are the major components included in the APK or IPA file of a Flutter app:

Compiled Dart code: This is the optimized machine code generated by the AOT compiler from the Dart code. It contains the app's business logic, UI definition, and other functionality.

Flutter engine: This is a native library that provides the runtime environment for the app. It includes the Dart runtime, Skia graphics engine, and other low-level components required to render the UI and interact with the device hardware.

Assets: These are static files such as images, fonts, and other resources required by the app. They are packaged along with the app and can be accessed at runtime.

Manifest file: This is an XML file that provides information about the app to the operating system, such as the app's package name, version, and required permissions.

Resources: These are compiled resources such as layouts, strings, and styles that are used by the app at runtime. They are packaged in binary format and can be accessed by the app using the resource IDs.

Native libraries: These are compiled code libraries in native language such as C or C++ used by the app to interact with the operating system and device hardware.


Although the Dart kernel itself is platform-independent, the Ahead-of-Time (AOT) compilation process for iOS and Android may differ. This is because the AOT compilation process involves generating platform-specific native code from the Dart kernel, which is then bundled with the app for deployment on the respective platform.

For example, on Android, the AOT compilation process generates native ARM code that is optimized for the target device's architecture. On iOS, the AOT compilation process generates native code for the device's ARM64 architecture. The AOT-compiled native code is then bundled along with the Dart kernel and the Flutter engine into the APK or IPA package for deployment on the respective platform.

The AOT-compiled native code is the optimized machine code that is produced by the AOT compiler from the Dart code. It is the code that is actually executed by the device's processor when the app is launched. By compiling the Dart code ahead of time, the AOT compiler can optimize the code for the specific device and platform, resulting in faster startup times, better performance, and smaller app sizes.

By bundling the AOT-compiled native code along with the Dart kernel and the Flutter engine, the app package becomes self-contained and can be easily installed and run on the target platform without the need for any additional dependencies or tools.


---

#### TIP: Layout Explained By Randal Schwartz 
```bash
LayoutBuilder(
          builder: (context, constraints) => switch (constraints.maxWidth) {
            > 1600 => const Placeholder(color: Colors.red),
            > 1400 => const Placeholder(color: Colors.orange),
            > 1200 => const Placeholder(color: Colors.yellow),
            > 1000 => const Placeholder(color: Colors.green),
            _ => const Placeholder(color: Colors.blue),
          },
        ),
        
        
        
class MyHomePage extends StatelessWidget {
  const MyHomePage({
    super.key,
  });

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      // appBar: AppBar(
      //   title: Text('Hello World!'),
      // ),
      body: SafeArea(
        child: LayoutBuilder(
          builder: (context, constraints) => ColoredBox(
            color: switch (constraints.maxWidth) {
              > 1600 => Colors.red,
              > 1400 => Colors.orange,
              > 1200 => Colors.yellow,
              > 1000 => Colors.green,
              _ => Colors.blue,
            },
            child: const Placeholder(),
          ),
        ),
        // floatingActionButton: MyFAB(),
      ),
    );
  }
}
```
---

 #### Q. does flutter have a built in widget to make a popup menu like this?

Ans at it's core it's just a dialog.  Here is a walkthrough: https://www.kindacode.com/article/flutter-showing-a-context-menu-on-long-press/


---

#### Q. Is there a way to get a Make text with colour gredient.

```bash
Tip: import 'package:flutter/material.dart';

class GradientText extends StatelessWidget {
  const GradientText(
    this.text, {
    required this.gradient,
    this.style,
  });

  final String text;
  final TextStyle? style;
  final Gradient gradient;

  @override
  Widget build(BuildContext context) {
    return ShaderMask(
      blendMode: BlendMode.srcIn,
      shaderCallback: (bounds) => gradient.createShader(
        Rect.fromLTWH(0, 0, bounds.width, bounds.height),
      ),
      child: Text(text, style: style),
    );
  }
}

// Usage
GradientText(
  'Hello Flutter',
  style: const TextStyle(fontSize: 40),
  gradient: LinearGradient(colors: [
    Colors.blue.shade400,
    Colors.blue.shade900,
  ]),
),
```
---

#### Q. Is there a way to get a scrollbar on a Text() or really a SelectableText() widget? Struggling to find any kind of documentation on text and scrollbars.

Tip: if the text is width-constrained it will wrap. and if it has maxlines, it will scroll.

---

#### Q. I'm having issues with ListView/ScrollablePositionedList Not all of my widgets have the same height. This results in the scrollbar becoming erratic. There are issues open on github, but I can't seem to find a reliable fix or solution. Anyone know of any? 

Tip: Column wrapped with a SingleChildScrollView worked like a charm

---

#### Q  How to get UI specific to Android and iOS?

Tip: flutter_platform_widgets | Flutter Package (pub.dev) https://pub.dev/packages/flutter_platform_widgets.

--- 

#### Q Is there a way to have a widget auto size the minimum size needed to avoid the layout overflow error? for Example, a list item that corresponds in height to the amount of text it holds?

Tip: wrap in intresic height weidget 

---

#### Q. To cache the image and don’t let them reload as list always load items visible on screen.

Tip: Use cacheExtent: & https://pub.dev/packages/cached_network_image to cache localy. 

---


#### Q. how do I achieve a typical chat app behaviour, so that once I open the keyboard, the latest message sticks to the top of the keyboard?

Tip: Pretty sure you can just enable resizeToAvoidBottomInset in the Scaffold to get that behavior.

---

#### Q. Package to check internet connectivity?

Tip: https://medium.com/@anslemAnsy/optimizing-widget-layout-for-flutter-homepage-with-real-time-internet-connectivity-status-f928118aa6c1 check this.

---

#### Q. Do any of the routing packages let you have multiple routing stacks?  i.e. to allow a user to have two or more "stateful" screens and they can move around those screens almost as if they were independent apps.  Each screen would have its own path/stack and stateful things like scroll position and selected tab and highlighted text or whatever.

Tip: https://pub.dev/packages/beamer

---

#### Q. is this code 
```bash
state = state == null ? 1 : state + 1;
equivalent to this? 
 state = state! + 1;
 ```
 Tip: The second one says "I promise it is not null. What you want is state = (state ?? 0) + 1;
 
---
 
#### Q. example for app architecture?
 
 Tip. i think it's this one: https://codewithandrea.com/articles/flutter-project-structure/
 
---
 #### Q. Immutability and riverpod 
 Tip.Immutability and reverpod. you should also look into making your lists immutable using a package like $[fast_immutable_collections], otherwise riverpod won't be able to tell when individual items in your lists change.
 
  https://pub.dev/packages/fast_immutable_collections
  
---

#### Q. When it comes to logging packages for Flutter, there are several options available. Here are some of the best logging packages for Flutter and their features:

1. Logger package
- The Logger package is one of the most popular logging solutions for Flutter. It has out-of-the-box support for logging and creates concise logs.
- It supports logging at different levels, including verbose, debug, info, warning, error, and wtf (what a terrible failure).
- Its logs are color-coded and support multiple output destinations, such as the console, files, and remote servers.
- It also supports logging with metadata, such as the time, logger name, and line number.
- You can find the entire GitHub repository for the Logger package [here](https://github.com/leisim/logger).

2. FLogs package
- The FLogs package is a lightweight logging package for Flutter.
- It supports logging at different levels, such as debug, info, warning, and error.
- Its logs are color-coded and support multiple output destinations, such as the console, files, and remote servers.
- It also supports logging with metadata, such as the time, logger name, and line number.
- You can find the entire GitHub repository for the FLogs package [here](https://github.com/Flutterando/flogs).

3. Loggy package
- The Loggy package is a simple logging package for Flutter.
- It supports logging at different levels, such as debug, info, warning, and error.
- Its logs are color-coded and support the console output destination.
- It also supports logging with metadata, such as the time, logger name, and line number.
- You can find the entire GitHub repository for the Loggy package [here](https://github.com/iamSahdeep/loggy).

It's important to note that while these are some of the best logging packages for Flutter, there are other options available as well. When choosing a logging package, consider the following factors:

- What output destinations do you need (console, files, remote servers)?
- What log levels do you need?
- What metadata do you need?
- What is the size of the package?
- What is the level of community support and documentation available for the package?

It's also worth noting that logging is not a replacement for proper error handling and debugging practices. While logging can provide valuable insights into the behavior of your application, it's important to have a well-defined error handling and debugging system in place as well.
Heh.  Logger is good.  the other two don't exist. 🙂
https://tleapps.com/best-flutter-packages-to-print-beautiful-logs/
TLe Apps
admin
5 Best Flutter Logging Packages for Debugging in 2023 - TLe Apps
Logging is an important part of programming, especially when it comes to debugging. In IDEs, it is usually located on the lower right-hand side of the window.
5 Best Flutter Logging Packages for Debugging in 2023 - TLe Apps

---
#### Q More about Logging package

package:logging is from the dart team
that'd probably be the safest one, although not necessarily the most featureful or popular
Here's an example of how you might use the logging package in a Dart program:

```bash
import 'package:logging/logging.dart';

void main() {
  // Configure the logging level and add a handler for the log messages
  Logger.root.level = Level.ALL; // defaults to Level.INFO
  Logger.root.onRecord.listen((record) {
    print('\${record.level.name}: \${record.time}: \${record.message}');
  });

  // Create a Logger with a unique name to easily identify the source of the log messages
  final log = Logger('MyClassName');

  // Example of logging a debug message and an error
  var future = doSomethingAsync().then((result) {
    log.fine('Got the result: \$result');
    processResult(result);
  }).catchError((e, stackTrace) => log.severe('Oh noes!', e, stackTrace));
}

```
This code sets up a simple logging configuration that logs all messages via print. It sets the root Level to Level.ALL, which means that all messages at or above this level are sent to the onRecord stream. Then it listens on the onRecord stream for LogRecord events and prints them out.

A Logger is created with a unique name to easily identify the source of the log messages. In this example, a debug message is logged using log.fine() when a result is received from an asynchronous operation, and an error is logged using log.severe() if an error occurs².

Would you like more information on this topic?

Source: Conversation with Bing, 4/23/2023
(1) logging | Dart Package. https://pub.dev/packages/logging.
(2) quick_log | Dart Package. https://pub.dev/packages/quick_log.
(3) Getting Started Quickly With Dart Logging - Scalyr Blog - SentinelOne. https://www.sentinelone.com/blog/started-quickly-dart-logging/.
(4) dart-lang/logging: A Dart package for debug and error logging. - Github. https://github.com/dart-lang/logging.
SentinelOne
Getting Started Quickly With Dart Logging - Scalyr Blog
Learn how to get started with Dart logging, and answer the questions what is application logging, why people do it, and what problems you may encounter.
Getting Started Quickly With Dart Logging - Scalyr Blog
bing chat makes the nicest pastable items for discord 🙂

---

#### Q Is there any package for complex layout

For unusual layouts => boxy 2.0.9 

---

#### Q. Help with chips wraped 

wrap list of chips - > there is widget called wrap 

---

#### Q Diff between null saFe & sound null safe?

null saFe -> Your code is null saFe and you are dependent on non null save dependencies. 

sound null safe -> code is null safe and all the dependencies are null safe.

---

#### Q Splash scereen setup for firebase data.

and make sure you're using the native_splash_screen package to define what to show before runapp()
yes
native splash screen can inform the OS what to show before your runapp starts
but that means you can execute code in main before runapp while that splash is showing.

Make signIn() async and have it return something that indicates if there is a user signed in.
Check that something - if there is a signed in user fetch the data.
```bash
Future<void> main() async {
  WidgetsBinding widgetsBinding = WidgetsFlutterBinding.ensureInitialized();
  WidgetsFlutterBinding.ensureInitialized();
  await PurchaseApi.init();
  await Firebase.initializeApp();
  FlutterNativeSplash.preserve(widgetsBinding: widgetsBinding);

  final user = await signIn();
  if (user != null) {
    await fetchMyData();
  }
  runApp(const HomePage());
}

```

