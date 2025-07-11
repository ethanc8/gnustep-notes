# Reference counting

## Basic rules

All objects have at least one **owner**. Idiomatic Cocoa code and code compiled with [Automatic Reference Counting](https://clang.llvm.org/docs/AutomaticReferenceCounting.html) follow the following rules:

* **You own objects you create**

This includes all objects you create using methods whose names start with `alloc`, `copy`, `mutableCopy`, and `new`, unless documented otherwise or it's obvious that they don't create objects. For example, `[NSObject alloc]` and `[NSObjectController newObject]` create objects, and you own the objects created by these items. Additionally, any object you create using a function or method which is marked with the macro `NS_RETURNS_RETAINED` is an object you create.

* **You own objects you retain**

If there is an object called `object`, you can retain the object using `[object retain]`.

* **You must release objects you no longer need**

If you no longer need the object called `object`, 


