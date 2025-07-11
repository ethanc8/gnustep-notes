# Needs to merge into GNUstep

## Foundation/NSObjCRuntime.h

* [X] NS_RETURNS_INNER_POINTER

## NSFileManager


* [X] `destinationOfSymbolicLinkAtPath:error:`
  * Workaround:
    * `pathContentOfSymbolicLinkAtPath:`
* [X] `-setAttributes:ofItemAtPath:error:`


## NSRegularExpression

* [X] [+escapedPatternForString:](https://developer.apple.com/documentation/foundation/nsregularexpression/1408386-escapedpatternforstring?language=objc)
  * Can't find a replacement in ICU
  * Need to quote: `* ? + [ ( ) { } ^ $ | \ .`
  * Example from MDN:
    ```javascript
    function escapeRegExp(string) {
      return string.replace(/[.*+?^${}()|[\]\\]/g, '\\$&'); // $& means the whole matched string
    }
    ```

## NSUndoManager

* [X] `-isRedoing` and `-isUndoing` need to be declared as properties:
  ```objc
  @property(readonly, getter=isUndoing) BOOL undoing;
  @property(readonly, getter=isRedoing) BOOL redoing;
  ```

## NSString

* [X] `-isAbsolutePath` needs to be declared as a property:
  ```objc
  @property(getter=isAbsolutePath, readonly) BOOL absolutePath;
  ```
* [X] `-localizedStandardCompare:`
  * Workaround: `-localizedCaseInsensitiveCompare:`
  * See [SO answer](https://stackoverflow.com/questions/15436143/string-comparison-for-localization):
    ```objc
    [aString compare:otherString
         options:NSCaseInsensitiveSearch | NSNumericSearch
         range:NSMakeRange(0,aString.length)
        locale:[NSLocale currentLocale]];
    ```

## NSSplitView

* [X] `NSSplitViewDelegate` needs to be declared as a protocol.

## NSTableCellView

* [ ] Completely unimplemented

## NSAlert

* [X] `-beginSheetModalForWindow:completionHandler:`