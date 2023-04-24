# Flutter-Dev-Discord-Tips-Tricks.
Flutter Dev Discord Tips &amp; Tricks.

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

..................................................................................................................................................................



..................................................................................................................................................................

..................................................................................................................................................................



..................................................................................................................................................................
