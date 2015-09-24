Overview
--------

Since MT4 build 880 was released, it's no longer easy to programmatically fill
values in Login dialog.

This library hides the complicated stuff and provides
easy to use API to login to any MT4 account from within MQL4 script/expert.


How to use
----------

```c
//+------------------------------------------------------------------+
//|                                                      ProjectName |
//|                                      Copyright 2012, CompanyName |
//|                                       http://www.companyname.net |
//+------------------------------------------------------------------+
#include <mql4-auth.mqh>
//+------------------------------------------------------------------+
//|                                                                  |
//+------------------------------------------------------------------+
void OnStart()
  {
// Just in case...
   if(loginDialogIsOpen()) closeLoginDialog();

// Let's do it!
   if(auth("ACCOUNT_NUMBER","PASSWORD","SERVER IP/HOSTNAME")) 
     {

      Print("Hooray, I found the login dialog, inserted credentials, now wait until MT4 connects :)");

        } else {

      Print("Sorry, I could not even find the Login dialog... Is your MT4 older than v880 or something?");

     }
  }
//+------------------------------------------------------------------+
```

Credits
-------

I think I scrapped half of the Internet while researching the topic related to
WinAPI and sending keyboard input messages programmatically and I was
trying everything I stumbled upon and was closing browser tabs here and there
to keep it clean so I lost some helpful resources but the ones that helped me
significantly and that I could remember are:

- [List of VK_ constants with their human readable meaning which I used in the beginning and it helped me finding the right track](https://msdn.microsoft.com/en-us/library/windows/desktop/dd375731(v=vs.85).aspx)

- [Forum topic with someone suggesting sending WM_CHAR instead of WM_KEYDOWN](https://facepunch.com/showthread.php?t=781744)

Notes
-----

MT4 release 880 made it extremely hard to programmatically authenticate from MQL4.
It was hard before release 880 too, but this time it was even harder.
Metatrader team, please don't make our lives so hard, we have more creative stuff to
concentrate on. Let's build beautiful solutions, not hackish workarounds.

License
-------

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to [<http://unlicense.org/>](http://unlicense.org)
