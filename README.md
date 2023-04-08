# Flutter-Dev-Discord-Tips-Tricks.
Flutter Dev Discord Tips &amp; Tricks.

Q. Is there a way to get a scrollbar on a Text() or really a SelectableText() widget? Struggling to find any kind of documentation on text and scrollbars.

Tip: if the text is width-constrained it will wrap. and if it has maxlines, it will scroll.

..................................................................................................................................................................

Q. I'm having issues with ListView/ScrollablePositionedList Not all of my widgets have the same height. This results in the scrollbar becoming erratic. There are issues open on github, but I can't seem to find a reliable fix or solution. Anyone know of any? 

Tip: Column wrapped with a SingleChildScrollView worked like a charm

..................................................................................................................................................................

Q  You can also use the flutter_platform_widgets if you want to have a UI specific to Android and iOS.

Tip: flutter_platform_widgets | Flutter Package (pub.dev) https://pub.dev/packages/flutter_platform_widgets

..................................................................................................................................................................
