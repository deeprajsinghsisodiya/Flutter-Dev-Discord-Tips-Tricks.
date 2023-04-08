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
