# Stdio.h



1. ## sprintf &&  sscanf

   ```c
   int sprintf( char          *buffer, const char          *format, ... );
   int sscanf( const char          *buffer, const char          *format, ... );
   ```

   ### Explain:

   Writes the results to a character string buffer.

   Read the data from null-terminated character string buffer.

2. ## getchar

   ```c
   int getchar(void);
   ```

   getchar return value is integer, so you will get a warn from some compiler by using:

   ```c
   char ch;
   ch = getchar()
   ```

   Because char value between in 0~255, but the return value of interger between in -2^31~2^31 - 1

3. ## fgets

   ```c
   char *fgets( char *restrict str, int count, FILE *restrict stream );
   ```

   `str` on success, null pointer on failure.

   If the end-of-file condition is encountered, sets the *eof* indicator on `stream` (see [feof()](https://en.cppreference.com/w/c/io/feof)). This is only a failure if it causes no bytes to be read, in which case a null pointer is returned and the contents of the array pointed to by `str` are not altered (i.e. the first byte is not overwritten with a null character).

   If the failure has been caused by some other error, sets the *error* indicator (see [ferror()](https://en.cppreference.com/w/c/io/ferror)) on `stream`. The contents of the array pointed to by `str` are indeterminate (it may not even be null-terminated).

