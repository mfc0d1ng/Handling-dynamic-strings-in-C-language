# Handle dynamic strings in C language
A shared library which provides a set of functions for handling dynamic strings in C.
<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/19289828/libstr.zip">here</a>
<h2>How to install?</h2>
Move libstr.so to /usr/lib
<h2>How to link?</h2>
In case you use gcc compiler, you can link the library to your C project as follows: gcc example.c -lstr \r
And don't forget to include string.h, note that string.h depends on string_details.h so keep both in your
project include directory.
