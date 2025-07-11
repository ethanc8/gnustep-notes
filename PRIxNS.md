# `PRIxNS` constants

```c
// On GNUstep systems
#if NSIntegerMax == INTPTR_MAX
#define PRIdNS PRIdPTR
#define PRIiNS PRIiPTR
#define PRIuNS PRIuPTR
#define PRIoNS PRIoPTR
#define PRIxNS PRIxPTR
#define PRIXNS PRIXPTR
#elif NSIntegerMax == LONG_MAX
// On Apple systems, long and NSInteger are the same.
// https://i.stack.imgur.com/ZLckY.png
#define PRIdNS "dl"
#define PRIiNS "il"
#define PRIuNS "ul"
#define PRIoNS "ol"
#define PRIxNS "xl"
#define PRIXNS "Xl"
#endif