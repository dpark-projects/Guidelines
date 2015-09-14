# Guidelines

General Principles
============

**Clarity**

###### It is good to be both clear and brief as possible, but clarity shouldn’t suffer because of brevity:


Code | Commentary
:------------ |-----:
insertObject:atIndex: | Good.
insert:at: | Not clear; what is being inserted? what does “at” signify?
removeObjectAtIndex: | Good.
removeObject: | Good, because it removes object referred to in argument.
remove: | Not clear; what is being removed?


In general, don’t abbreviate names of things. Spell them out, even if they’re long:

Code
Commentary

destinationSelection

Good.

destSel

Not clear.

setBackgroundColor:

Good.

setBkgdColor:

Not clear.

You may think an abbreviation is well-known, but it might not be, especially if the developer encountering your method or function name has a different cultural and linguistic background.

However, a handful of abbreviations are truly common and have a long history of use. You can continue to use them; see Acceptable Abbreviations and Acronyms.

Avoid ambiguity in API names, such as method names that could be interpreted in more than one way.


Code
Commentary

sendPort

Does it send the port or return it?

displayName

Does it display a name or return the receiver’s title in the user interface?


**Consistency**


Try to use names consistently throughout the Cocoa programmatic interfaces. If you are unsure, browse the current header files or reference documentation for precedents.
Consistency is especially important when you have a class whose methods should take advantage of polymorphism. Methods that do the same thing in different classes should have the same name.
Code
Commentary
- (NSInteger)tag
Defined in NSView, NSCell, NSControl.
- (void)setStringValue:(NSString *)
Defined in a number of Cocoa classes.
See also Method Arguments.

No Self Reference

Names shouldn’t be self-referential.
Code
Commentary
NSString
Okay.
NSStringObject


**Self-referential**

Constants that are masks (and thus can be combined in bitwise operations) are an exception to this rule, as are constants for notification names.
Code
Commentary
NSUnderlineByWordMask
Okay.
NSTableViewColumnDidMoveNotification
Okay.
