# Generic deque in C language
A shared library which provides a set of functions for handling deque operations in C. Note that the library doesn't provide methods for constructing and copying the vector 
elements because C isn't object-oriented programming language. User is responsible for constructing and copying the vector elements.

<h2>How to download?</h2>
You can download it <a href="https://github.com/user-attachments/files/19638695/libdeque.zip">here</a>

<h2>How to install?</h2>
Unzip the downloaded file and move libdeque.so to /usr/lib

<h2>How to link?</h2>
You can link the library to your C project as follows: gcc example.c -l vec <br>
And don't forget to include deque.h, note that deque.h depends on deque_details.h so keep both in the same directory.

