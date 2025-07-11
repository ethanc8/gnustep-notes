# macOS graphics stack

* [Mac Technology Overview - Media Layer](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/OSX_Technology_Overview/MediaLayer/MediaLayer.html#//apple_ref/doc/uid/TP40001067-CH273-SW1)

![Diagram of graphics stack, with UIKit / AppKit on top in a blue bubble, then a green bubble containing Core Animation, then Metal and Core Graphics as the second line, then Graphics Hardware as the third line](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CoreAnimation_guide/Art/ca_architecture_2x.png)

## Core Animation

Core Animation is the animation API on macOS and iOS, allowing animation of applications. Its CALayer also provides the basic surface on which most drawing is done. It's part of Quartz Core.

* [Manual](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/CoreAnimation_guide/Introduction/Introduction.html)
* [API reference](https://developer.apple.com/documentation/quartzcore?language=objc)
* [WWDC11 - Core Animation Essentials](https://www.wwdcnotes.com/notes/wwdc11/421/)

Implementations:
* [Islandwood/WinObjC]
  * [Design document with comments (2016 Nov)](https://github.com/microsoft/WinObjC/blob/develop/docs/CoreAnimation/WinObjc.Composition.and.Layout.docx)
* [GNUstep QuartzCore](https://github.com/gnustep/libs-quartzcore)
  * [Incomplete GSoC 2018 project to improve bridging with AppKit](https://gist.github.com/sbrki/efe8b94444946bde1bd3fa241071c8b2)
    * [Source for the project](https://github.com/sbrki/libs-quartzcore/tree/CAAppKitBridge-dev)
    * [Blog post #7](http://web.archive.org/web/20190921095925if_/https://blog.stjepan.io/google-soc-2018-diary-ep-7-making-it-draw/)
    * <stjepanbrkicc@gmail.com>

## Core Graphics / Quartz 2D

* [Manual](https://developer.apple.com/library/archive/documentation/GraphicsImaging/Conceptual/drawingwithquartz2d/Introduction/Introduction.html)
* [API reference](https://developer.apple.com/documentation/coregraphics?language=objc)

Implementations:
* [Islandwood/WinObjC](https://github.com/microsoft/WinObjC/tree/develop/Frameworks/CoreGraphics)
  * [Design document for Direct2D (2016 Oct)](https://github.com/microsoft/WinObjC/blob/develop/docs/CoreGraphics/CoreGraphics%20-%20Direct2D.docx?raw=true)
  * Two implementations:
    * [Cairo](https://github.com/microsoft/WinObjC/tree/0.1-preview/Frameworks/CoreGraphics)
    * Windows Direct2D (current)
* [GNUstep Opal](https://github.com/gnustep/libs-opal)
* [upstream Cocotron](https://github.com/cjwl/cocotron/tree/master/CoreGraphics)

## Core Text

Low-level C API for text handling.

* [Manual](https://developer.apple.com/library/archive/documentation/StringsTextFonts/Conceptual/CoreText_Programming/Introduction/Introduction.html#//apple_ref/doc/uid/TP40005533)
* [API reference](https://developer.apple.com/documentation/coretext?language=objc)

Implementations:
* [Islandwood/WinObjC](https://github.com/microsoft/WinObjC/tree/develop/Frameworks/CoreText)
  * [Design document (2017 Jan)](https://github.com/microsoft/WinObjC/blob/develop/docs/CoreText/WinObjC.CoreText.docx?raw=true)
  * Two implementations:
    * FreeType - mostly implemented from scratch
    * Windows DirectWrite (current)
* [ravynOS Cocotron](https://github.com/ravynsoft/ravynos/tree/main/Frameworks/CoreText)
* [darling-cocotron](https://github.com/darlinghq/darling-cocotron/tree/master/CoreText)
  * [Issues](https://github.com/darlinghq/darling/issues?q=is%3Aissue+coretext)
  * [Linux-only, darling-focused](https://github.com/darlinghq/darling/issues/365#issuecomment-495668493)
* [upstream Cocotron](https://github.com/cjwl/cocotron/tree/master/CoreText)

## Core OpenGL

> This section is just here to link to missing documentation. It's not actually
> that important.

Core OpenGL was deprecated in macOS 10.14 Mojave, but is still available. On Apple Silicon, it appears to be emulated via Metal. 

* [API reference](https://web.archive.org/web/20140812200349if_/https://developer.apple.com/library/mac/documentation/GraphicsImaging/Reference/CGL_OpenGL/Reference/reference.html)
* [OpenGL Extensions Guide](https://web.archive.org/web/20140604052652if_/https://developer.apple.com/library/Mac/documentation/GraphicsImaging/Conceptual/OpenGLExtensionsGuide/Reference/reference.html#//apple_ref/doc/uid/TP40001486)
* [OpenGL Programming Guide for Mac](https://developer.apple.com/library/archive/documentation/GraphicsImaging/Conceptual/OpenGL-MacProgGuide/opengl_intro/opengl_intro.html#//apple_ref/doc/uid/TP40001987)
* AppKit OpenGL:
  * [NSOpenGLView](https://developer.apple.com/documentation/appkit/nsopenglview?language=objc)
* [Supported versions of OpenGL on pre-2020 Macs](https://support.apple.com/en-us/HT202823)
* [OpenGL Capabilities Tables](https://web.archive.org/web/20140603020350if_/https://developer.apple.com/graphicsimaging/opengl/capabilities/)
* [Understanding and Detecting OpenGL Functionality](https://developer.apple.com/library/archive/technotes/tn2080/_index.html)
* [The case of OpenGL, in C++, on m1 mac](https://carette.xyz/posts/opengl_and_cpp_on_m1_mac/)
* [OpenGL headers](https://github.com/phracker/MacOSX-SDKs/tree/master/MacOSX11.3.sdk/System/Library/Frameworks/OpenGL.framework/Versions/A/Headers)
* [GLUT headers](https://github.com/phracker/MacOSX-SDKs/tree/master/MacOSX11.3.sdk/System/Library/Frameworks/GLUT.framework/Versions/A/Headers)
* [AGL headers](https://github.com/phracker/MacOSX-SDKs/tree/master/MacOSX11.3.sdk/System/Library/Frameworks/AGL.framework/Versions/A/Headers)

## References
