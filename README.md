# decipherer
  C++ Technical Task — Junior
  
  You're given a text file in English in ANSI encoding that has been encrypted using two ciphers — the Vigenère cipher and the Affine cipher, in arbitrary order. The task is to develop in C++ a console application that deciphers encrypted text for both of these ciphers, one at a time.
The command line will provide the application with the name of the encrypted file, output file name, the kind of cipher to use (ex. indicated by a letter), and the cipher key/parameters needed for decryption. The application should notify its user of improper command line usage and, in that case, describe how to use the application properly. The deciphered text file will contain readable text, so there will be no doubt as to whether the application's decryption works correctly — if your solution is correct, you will be able to read it, even though there will only be letters — no spaces or punctuation. The input file is supposed to contain lowercase latin letters only. Incorrect command line input and incorrect file contents must be handled in some way — the application should not crash or demonstrate undefined behavior.
Since both ciphers are stateless, distinct parts of the text can be processed concurrently by multiple threads. A cornerstone of the technical task is to allow for multi-threaded deciphering, in any preferred way (ex. there may be a standalone thread per data chunk), and writing deciphered text into a shared container before writing to the output file. The shared container will need thread synchronization mechanisms for data integrity to be preserved.
The application holds no commercial value, the point of the task is to assess your technical skills at a calm pace and in your comfortable environment. Not only does the application have to work correctly, but its design must reflect the necessary developer skills, and so the following will be assessed:
application architecture — OOP is necessary
code readability and style
thread communication design
error handling strategy
In development of the application you are only permitted to use the C++ Standard Library and OS-dependent libraries (Windows API, POSIX, etc.). Using any other third-party libraries is strictly prohibited.
To decipher the given file, the application has to be run twice, once for each cipher. When you're done with the task, please e-mail us back a .zip of your solution with the deciphered file enclosed.
View the next page for some example input and output.Example 1.
Input file “encrypted.txt”:
software
Command line:
./decipherer encrypted.txt plain.txt vig software
Output file “plain.txt”:
aaaaaaaa
Example 2.
Command line:
./decipherer
Console output:
./decipherer input-file output-file cipher[vig/aff] parameters[vig_key/aff_a_b}
Example 3.
Command line:
./decipherer nonexistent.txt plain.txt aff 5 1
Console output:
Input file not found.
Example 4.
Input file “messed_up.txt”:
ÀÚ¨ÉäÐ¨16:º4ïâ&û9²·ù
Command line:
./decipherer messed_up.txt plain.txt aff 5 1
Output file “plain.txt” is empty, wrong characters have been removed.
