# How-to-bypass-Windows-Defender-with-Embedded-Resources-.rsrc-

Sample source files for the video posted on Gemini Cyber Security Youtube channel:

https://www.youtube.com/@gemini_security

https://www.youtube.com/watch?v=36O2qDrHQnk

## credits for the references/files used:

demo.rc - template resource .rc file:

https://blog.didierstevens.com/2018/09/17/quickpost-compiling-exes-and-resources-with-mingw-on-kali/

aes.py - for aes encryption and DecryptAES function:

https://github.com/TheD1rkMtr/FilelessPELoader/tree/main

helloworld.cpp - Resource APIs usage:

https://www.ired.team/offensive-security/code-injection-process-injection/loading-and-executing-shellcode-from-portable-executable-resources

---

Rich added

# build malware

helloworld.cpp
```
#include <stdio.h>

int main() {
    printf("Richard Jones, Learning C++!");
    return 0;
}
```

## Compile (kali)
```
x86_64-w64-mingw32-g++ -o hello.exe helloworld.cpp
```

Add icon (get demo.rc file and an icon file called demo.ico)
```
https://github.com/AssassinUKG/How-to-bypass-Windows-Defender-with-Embedded-Resources-.rsrc-/blob/main/demo.rc
```

## build .rsrc
```
x86_64-w64-mingw32-windres demo.rc -o demo.o
```


## build exe
```
x86_64-w64-mingw32-g++ -o hello.exe helloworld.cpp demo.o
```

https://www.youtube.com/watch?v=36O2qDrHQnk
