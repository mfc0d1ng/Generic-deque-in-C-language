# Generic deque in C language
A shared library which provides a set of functions for handling deque operations in C. Note that the library doesn't provide methods for constructing and copying the deque 
elements because C isn't object-oriented programming language. User is responsible for constructing and copying the deque elements.

<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/19640046/libdeque.zip">here</a>

<h2>How to install?</h2>
Unzip the downloaded file and move libdeque.so to /usr/lib

<h2>How to link?</h2>
You can link the library to your C project as follows: gcc example.c -l deque <br>
And don't forget to include deque.h, note that deque.h depends on deque_details.h so keep both in the same directory.

<br>
<h2> Examples </h2>

* Example A:

<pre>
<code class="language-c">
#include &lt;stdio.h&gt;
#include &lt;stdlib.h&gt;
#include "deque.h"

int main()
{
    /* Construct stack */
    deque stack = deque_new(int);

    /* Push data into stack */
    for (size_t i = 0; i < 10; i++)
    {
        deque_push_front(int, &stack, i);
    }

    puts("Contents of stack is: ");
    while (!deque_empty(&stack))
    {
        /* Print the top element in stack */
        printf(" %i\n", deque_front(int, &stack));
        /* Pop the top element in stack */
        deque_pop_front(&stack);
    }
    
    /* Erase stack */
    deque_destructor(&stack);    
    
    return EXIT_SUCCESS;
}
</code>
</pre>

* Example B:

<pre>
<code class="language-c">
#include &lt;stdio.h&gt;
#include &lt;stdlib.h&gt;
#include "deque.h"

int main()
{
    /* Construct chars */
    deque chars = deque_new(char);

    deque_push_back(char, &chars, 'C');
    deque_push_front(char, &chars, 'B');

    deque_push_back(char, &chars, 'D');
    deque_push_front(char, &chars, 'A');

    puts("Contents of chars is: ");
    for (char* it = deque_begin(&chars); it != deque_end(&chars); ++it)
    {
        printf("%c ", *it);
    }
    
    deque_destructor(&chars);
    
    return EXIT_SUCCESS;
}
</code>
</pre>

