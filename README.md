# Flutter-Dev-Discord-Tips-Tricks.
Flutter Dev Discord Tips &amp; Tricks.
Q. Is there a way to get a Make text with colour gredient.

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

..................................................................................................................................................................

Q. Is there a way to get a scrollbar on a Text() or really a SelectableText() widget? Struggling to find any kind of documentation on text and scrollbars.

Tip: if the text is width-constrained it will wrap. and if it has maxlines, it will scroll.

..................................................................................................................................................................

Q. I'm having issues with ListView/ScrollablePositionedList Not all of my widgets have the same height. This results in the scrollbar becoming erratic. There are issues open on github, but I can't seem to find a reliable fix or solution. Anyone know of any? 

Tip: Column wrapped with a SingleChildScrollView worked like a charm

..................................................................................................................................................................

Q  How to get UI specific to Android and iOS?

Tip: flutter_platform_widgets | Flutter Package (pub.dev) https://pub.dev/packages/flutter_platform_widgets.

..................................................................................................................................................................

Q Is there a way to have a widget auto size the minimum size needed to avoid the layout overflow error? for Example, a list item that corresponds in height to the amount of text it holds?

Tip: wrap in intresic height weidget 

..................................................................................................................................................................

Q. To cache the image and don’t let them reload as list always load items visible on screen.

Tip: Use cacheExtent: & https://pub.dev/packages/cached_network_image to cache localy. 

..................................................................................................................................................................


Q. how do I achieve a typical chat app behaviour, so that once I open the keyboard, the latest message sticks to the top of the keyboard?

Tip: Pretty sure you can just enable resizeToAvoidBottomInset in the Scaffold to get that behavior.

..................................................................................................................................................................

Q. Package to check internet connectivity?

Tip: https://medium.com/@anslemAnsy/optimizing-widget-layout-for-flutter-homepage-with-real-time-internet-connectivity-status-f928118aa6c1 check this.

..................................................................................................................................................................

Q. Do any of the routing packages let you have multiple routing stacks?  i.e. to allow a user to have two or more "stateful" screens and they can move around those screens almost as if they were independent apps.  Each screen would have its own path/stack and stateful things like scroll position and selected tab and highlighted text or whatever.

Tip: https://pub.dev/packages/beamer

..................................................................................................................................................................

Q. is this code 
state = state == null ? 1 : state + 1;
equivalent to this? 
 state = state! + 1;
 
 Tip: The second one says "I promise it is not null. What you want is state = (state ?? 0) + 1;
 
 ..................................................................................................................................................................
 
 Q. example for app architecture?
 
 Tip. i think it's this one: https://codewithandrea.com/articles/flutter-project-structure/
 
 ..................................................................................................................................................................
 
 Tip.Immutability and reverpod. you should also look into making your lists immutable using a package like $[fast_immutable_collections], otherwise riverpod won't be able to tell when individual items in your lists change.
 
  https://pub.dev/packages/fast_immutable_collections
  
  ..................................................................................................................................................................
  
  
  
  
  
  When it comes to logging packages for Flutter, there are several options available. Here are some of the best logging packages for Flutter and their features:

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

..................................................................................................................................................................

package:logging is from the dart team
that'd probably be the safest one, although not necessarily the most featureful or popular
Here's an example of how you might use the logging package in a Dart program:

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

..................................................................................................................................................................

For unusual layouts => boxy 2.0.9 

..................................................................................................................................................................

wrap list of chips - > there is widget called wrap 

..................................................................................................................................................................

null save -> Your code is null save and you are dependent on non null save dependencies. 

sound null safe -> code is null safe and all the dependencies are null safe.

..................................................................................................................................................................

Q Splash scereen setup for firebase data.

and make sure you're using the native_splash_screen package to define what to show before runapp()
yes
native splash screen can inform the OS what to show before your runapp starts
but that means you can execute code in main before runapp while that splash is showing.

Make signIn() async and have it return something that indicates if there is a user signed in.
Check that something - if there is a signed in user fetch the data.
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




..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................
