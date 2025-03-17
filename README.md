# Handling dynamic strings in C language
A shared library which provides a set of functions for handling dynamic strings in C.
<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/19293697/libstr.zip">here</a>
<h2>How to install?</h2>
Move libstr.so to /usr/lib
<h2>How to link?</h2>
You can link the library to your C project as follows: gcc example.c -lstr <br>
And don't forget to include string.h, note that string.h depends on string_details.h so keep both in the same directory.

<p1> Examples </p1>
* Constructing string object
<pre style="color: rgb(243, 243, 232); background-color: #000; font-size: large; font-weight: bold; width: 600px;">
        <code class="language-c">
            #include &lt;stdio.h&gt;
            #include &lt;stdlib.h&gt;
            #include "string.h"
            
            int main()
            {
                /* Construct s1 */
                string s1 = string_new();
            
                /* Construct s2 */
                string s2 = string_from("Hello world");
                            
                return EXIT_SUCCESS;
            }
        </code>
    </pre>
    
