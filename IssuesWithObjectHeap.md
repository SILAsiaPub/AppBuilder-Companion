## Issue with *object heap* <a id="h2-5"></a>

- [Readme](README.md)

32 bit OS or 64 bit OS running 32 bit Java seem to have an issue with the **object heap** size. 

To fix this do the following:

1. Create this file: C:\\Users\\yourname\\.gradle\\gradle.properties
2. Add the following line:<br />
  org.gradle.jvmargs=-XX\:MaxHeapSize\=256m -Xmx256m
3. Close SAB, reopen and try and build again.