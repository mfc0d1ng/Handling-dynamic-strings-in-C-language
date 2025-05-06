# Handling dynamic strings in C language
A shared library which provides a set of functions for handling dynamic strings in C.

<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/20054870/libstr.zip">here</a>

<h2>How to install?</h2>
Unzip the downloaded file and move libstr.so to /usr/lib

<h2>How to link?</h2>
You can link the library to your C project as follows: gcc example.c -l str

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

    /* Append multiple characters to s1 */
    string_push(&s1, 'B');
    string_push(&s1, 'C');

    /* Insert character 'A' at the beginning of s1 */
    string_insert(&s1, string_begin(&s1), 'A');

    /* Append a string to s2 */
    string_append(&s2, " 2025");

    /* Getting a pointer to the contents of s1 */
    const char* content1 = string_c_str(&s1);
    printf("s1 = %s\n", content1);
    /* Getting a pointer to the contents of s2 */
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

* Example B:

<pre>
<code class="language-c">
#include &lt;stdio.h&gt;
#include &lt;stdlib.h&gt;
#include "string.h"

#define $(__s)   string_from(__s)

int main()
{
    /* Create array of strings (fruits) */
    string fruits[] = {$("strawberry"), $("apple"), $("pineapple"), $("banana")};

    /* Sort array fruits */
    qsort(fruits, sizeof(fruits)/sizeof(string), sizeof(string), string_ascending);
    
    /* Print array fruits */
    for (size_t i = 0; i < sizeof(fruits)/sizeof(string); i++)
    {
        /* Iterator into array fruits */
        string* it = fruits + i;
        /* Print the string referenced by the iterator 'it' */
        puts(string_c_str(it));
        /* Erase the string referenced by the iterator 'it' */
        string_destructor(it);
    }
    
    return EXIT_SUCCESS;
}
</code>
</pre>
