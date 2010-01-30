About This Package
==================

Here are some Xcode text macros I use for writing Objective-C code.
They speed up my coding a lot, especially the macros for methods.

Let me know if you wrote useful macros that you would like to add
to this collection. The best way is by forking this project on github,
adding your macros, and sending me a pull request.

There is also a cheat sheet generator that lists the macros on an HTML
page with their completion prefixes and your keybord shortcuts.
Here’s an [example](http://www.entropy.ch/software/macosx/xcode-macro-cheat-sheet.html).
You’re more than welcome to spice up that HTML in the XSLT:-)


About Xcode’s Text Macros in General
====================================

* Assigning keyboard shortcuts to the most often used macros is *highly*
  recommended, especially to get one of the coolest text macro features,
  cycle lists. Cycle lists link together related macros and let you
  quickly flip through them by repeatedly pressing the shortcut. This
  is very useful for different variants of `if ()` statements, for example.
  Until recently I didn’t even know about cycle lists.
* Another great feature that’s easier to use with keyboard shortcuts is
  the ability of some macros to wrap selected text. Again this is useful
  for `if ()` statements, and especially so in combination with the previous
  feature. Select a bunch of lines, hit the shortcut to wrap them in an
  `if ()` block, and hit the shortcut again to switch to an `if / else` block.
  Taken together, this results in a killer feature.
* I recommend picking a simple and consistent keyboard shortcut convention
  across all macros. I use just the Ctrl key with letters. Obviously
  this only works because I don’t use the emacs text editing bindings,
  except maybe Ctrl-T once in a while. My recommendations are listed below
  in the macro list. You could also use the number keys with Cmd-Ctrl.
  Whatever you pick, if it is something simple and unified, you’ll have
  an easier time remembering the shortcuts, and only if you remember and
  use them a lot will you get the full time-saving benefit.
* Xcode’s macro language is fairly complicated, and as far as I know not
  well-documented, but it is also very powerful because it uses an inheritance
  system and flexible token replacement features. It’s worth to learn it,
  and you can learn a lot by looking at the built-in `C.xctxtmacro` file.
  The built-in macro files are in the Xcode application bundle in
  `Contents/PlugIns/TextMacros.xctxtmacro/Contents/Resources/`.
* The Xcode user defaults also influence the macros, specifically the whitespace.
  These defaults are documented [here](http://developer.apple.com/mac/library/documentation/DeveloperTools/Reference/XcodeUserDefaultRef/100-Xcode_User_Defaults/UserDefaultRef.html#//apple_ref/doc/uid/TP40005535-CH3-SW40).


About the Macros
================

With all of these, play around a bit, with something selected, nothing
selected etc. to see what gets wrapped, where the cursor ends up, what
placeholders get inserted.

Installation
------------

Put the .xctxtmacro file into your

    "$HOME/Library/Application Support/Developer/Shared/Xcode/Specifications/"

directory. Then restart Xcode so it picks them up. *Definitely* assign keyboard
shortcuts :-)

Here’s a quick run-down of some of the macros:

Objective-C String Literal
--------------------------

Inserts `@""`. If something is selected, it puts that between the quotes.
Without selection, moves the cursor between the quotes.

Recommended shortcut: ⌃\

NSLog() Calls
-------------

Inserts `NSLog()` calls with zero and one arguments. The two are linked
in a cycle list.

Recommended shortcut: ⌃L

Single-Statement if ()
----------------------

Inserts an `if ()` statement without the braces. It’s linked to several
other `if ()` statement variants in a cycle list.

Recommended shortcut: ⌃I

Method Definitions
------------------

Several variants of methods with different return value and parameter
combinations. They are linked together in a cycle list.

Recommended shortcut: ⌃M

Method Parameter
----------------

Inserts an `xxxx:(yyy)zzz` sequence to add a parameter to a method
definition/declaration. Ideal for combination with the method
blocks in the previous item.

Recommended shortcut: ⌃P


About the Cheat Sheet Generator
===============================

The cheat sheet generator reads the macros in Apple’s C and
Objective-C files built in to Xcode. By default it doesn’t
read the shortcuts for C++ or the other languages supported
by Xcode, because I don’t use those and don’t want them cluttering
up the list. If you want them you can enable them in the generator’s
`read_macro_definitions()` method.

It reads *all* of the `.xctxtmacro` files in your personal
directory, as it is likely that you care a lot about those...



