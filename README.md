# Handling dynamic strings in C language
A shared library which provides a set of functions for handling dynamic strings in C.
<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/19293697/libstr.zip">here</a>
<h2>How to install?</h2>
Move libstr.so to /usr/lib
<h2>How to link?</h2>
You can link the library to your C project as follows: gcc example.c -lstr <br>
And don't forget to include string.h, note that string.h depends on string_details.h so keep both in the same directory.
<br>
<h2> Examples </h2>
* Example A:

<pre>
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

    /* Append multiple characters to the string s1 */
    string_push(&s1, 'B');
    string_push(&s1, 'C');
    string_push(&s1, 'D');
    string_push(&s1, 'E');

    /* Insert character 'A' at the beginning of the string s1 */
    string_insert(&s1, string_begin(&s1), 'A');

    /* Append a string to the string s2 */
    string_append(&s2, " 2025");

    /* Pointer to the contents of the string s1 */
    const char* content1 = string_c_str(&s1);
    printf("s1 = %s\n", content1);
    /* Pointer to the contents of the string s2 */
    const char* content2 = string_c_str(&s2);
    printf("s2 = %s\n", content2);

    /* Erase s1 */
    string_destructor(&s1);
    /* Erase s2 */
    string_destructor(&s2);
                
    return EXIT_SUCCESS;
}
</code>
</pre>
