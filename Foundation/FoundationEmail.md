# The future of Foundation and CoreFoundation

> **NOTE:** This is an early draft, and the most important parts of the email are not written yet.

tldr: Apple is rewriting its Foundation and CoreFoundation in Swift.

This email is going to be kind of long and go into some of the history; the new stuff will be at the end in the "Swift's path - Swift Foundation" section.

## Origins in EOF and OpenStep, and evolution into Mac OS X

NeXTstep originally used an ANSI Smalltalk-style standard library for its root class, collections, and other standard library functions. In 1994, NeXT released the Enterprise Objects Framework (EOF), a database framework (which heavily influenced our own GDL2). [In order to support EOF](https://www.nextop.de/NeXTstep_3.3_Developer_Documentation/Foundation/HybridWorld.htmld/index.html), NeXT introduced the Foundation Kit with its own class hierarchy descending from NSObject. Later in 1994, NeXT integrated the Foundation Kit into their OpenStep standard shared with Sun, and released a much improved version in OPENSTEP 4.0 (their OpenStep implementation on top of Mach).

In 1997, NeXT was acquired by Apple, and OPENSTEP development continued as Rhapsody. Apple began trying to build a path for migration from classic Mac OS to their new OPENSTEP derivative. Initially, the OpenStep APIs were renamed "Yellow Box", and they created a Mac OS emulator called "Blue Box". However, as Rhapsody evolved into Darwin/Mac OS X, Apple decided that they needed to support C applications with a Mac OS-like API to ease porting. They introduced the Carbon framework for this, and to help share collections between Carbon and Cocoa (formerly Yellow Box) and provide a collection library for C code, they introduced CoreFoundation, a set of many important standard library classes, which Foundation was reimplemented on top of. Mac OS X became split into Darwin -- the core OS -- and macOS, iOS, tvOS, watchOS, etc -- various OSes built on Darwin. This was the paradigm for the next twenty or so years.

Apple made parts of CoreFoundation portable to Windows and used it inside iTunes and possibly inside other Apple applications for Windows. This port was released on opensource.apple.com under the Apple Public Source License, a GPL-incompatible copyleft license, and was called CFLite.

## GNUstep's path

> **Note**: You can read more about GNUstep at http://gnustep.made-it.com/Guides/History.html.

In 1991, Paul Kunz and others from Stanford Linear Accelerator Center had written an implementation of the NeXT Application Kit (the pre-OpenStep one, with the `NX`* classes) so that they could port their HippoDraw app to other systems, which was called `objcX`. Meanwhile, Andrew McCallum began writing an implementation of the NeXT standard library, called `libcoll`. In 1994, as NeXT and Sun began developing OpenStep, Andrew McCallum and the SLAC team began combining their work into a single implementation of the then-current NeXT and OpenStep APIs. This work continued into 1998, when GNUstep was finally combined into a single cohesive software package. In the 2000s and 2010s, there were also other Foundation implementation such as libFoundation, so GNUstep Make supported building on top of those other Foundation immplementations too. Since then, GNUstep has continued on its path of a Foundation implementation called GNUstep Base, without any dependency on CoreFoundation.

### CoreFoundations for GNUstep

GNUstep's CoreFoundation implementation, CoreBase, has always been on top of Foundation. It accomplishes bridging differently from how CoreFoundation on macOS does it; I don't know exactly how this works.

I have separately been working on an implementation of CoreFoundation based on the CoreFoundation in swift-corelibs-foundation. I'll discuss this in "Swift's path".

## Swift's path - Core Libraries

The Swift language was announced at WWDC 2014, and the Linux port was published in December 2015 [1]. When the Linux port was published, a new Swift implementation of Foundation, `swift-corelibs-foundation`, was included along with it to make porting easier, provide reference types for standard collections, and provide useful classes like Streams and RunLoops. `swift-corelibs-foundation` was based on Apple's CoreFoundation, and was licensed under Apache-2.0. It was quite incomplete and progress on it was slow. Apple continued to rebase it on newer CoreFoundations on a yearly basis, and stopped publishing CFLite (the CoreFoundation inside `swift-corelibs-foundation` was fairly complete). This CoreFoundation was supposed to be treated as an implementation detail of `swift-corelibs-foundation` [2], but as it was fairly complete I forked it and added support for building with GNUstep Make and bridging with Objective-C to my fork [3].

[1] https://www.swift.org/blog/swift-linux-port/
[2] https://github.com/swiftlang/swift-corelibs-foundation
[3] https://github.com/ethanc8/

## Cocotron's path



## WinObjC's path



## Darling's path



## Swift's path - Swift Foundation

In December 2022, Apple announced it was writing a new Foundation implementation without any CoreFoundation dependencies called Swift Foundation [1][2]. 

[1] https://www.swift.org/blog/future-of-foundation/
[2] https://forums.swift.org/t/what-s-next-for-foundation/61939

* https://forums.swift.org/t/any-updates-on-the-new-foundation/68532
* https://www.swift.org/blog/foundation-preview-now-available/
* 
* https://github.com/swiftlang/swift-corelibs-foundation/issues/5001
* https://forums.swift.org/t/swift-foundation-now-available/73530a
* https://github.com/swiftlang/swift-foundation
* 

## Questions for the future

1. Do we want to prioritize Swift bridging so that we can use swift-foundation as a Foundation implementation and therefore use a similar Foundation as Apple is using?
    - Swift bridging seems to be a quite large endeavor
2. If Apple introduces Swift-only APIs to Foundation, will we provide an Objective-C implementation of those in GNUstep Base?
3. In the near future (before swift-foundation is ready), which CoreFoundation implementation should we use?
    - CoreBase
    - My CoreFoundation fork based on Catalina (10.15) CoreFoundation
    - Make a new fork off of Ventura (13.0) CoreFoundation
    - Something else???
4. 
