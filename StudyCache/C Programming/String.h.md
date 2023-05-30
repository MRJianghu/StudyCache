<h1 align = "center">String.h</h1>

1. ## strcnpy

   ```c
   char *strncpy( char *dest, const char *src, size_t count );
   ```

   ​	This function forces the copying of conut bytes from src to dest，wehter the size of the dest and src. 

   ​	So, ensuring the size of dest and src length is greater than the count.

   ​	In order to print dest correctly, ensure the count is greater than the `src` length

2. ## strlen

   ```c
   size_t strlen (const char *s)
   ```

   The real size of a null-determinated byte string pointed by `s`. 

3. ### strcpy

   ```c
   char *
   STRCPY (char *dest, const char *src)
   {
     return memcpy (dest, src, strlen (src) + 1); // find '\0'
   }
   ```

   This function will cpoy `src` to `dest` and also copy the '\0' from `src`. 

4. ## strcmp

   ```c
   int strcmp( const char *lhs, const char *rhs );
   ```

   The behavior is undefined if `lhs` or `rhs` are not pointers to null-terminated byte strings.

   ### Rerurn value

   - Negative value if `lhs` appears before `rhs` in lexicographical order.

   - Zero if `lhs` and `rhs` compare equal.

   - Positive value if `lhs` appears after `rhs` in lexicographical order.

5. ## strncmp

6. ## strstr

7. ## strchr

   Pointer to the found character in `str`, or null pointer if no such character is found.

8. ## strrchr

   ```c
   char *
   STRRCHR (const char *s, int c)
   {
     const char *found, *p;
   
     c = (unsigned char) c;
   
     /* Since strchr is fast, we use it rather than the obvious loop.  */
   
     if (c == '\0')
       return strchr (s, '\0');
   
     found = NULL;
     while ((p = strchr (s, c)) != NULL)
       {
         found = p;
         s = p + 1;
       }
   
     return (char *) found;
   }
   ```

   ​	Start from scratch。

9. ## strtok

   ```c
   char *strtok (char * s , const char * delim);
   ```

   #### Fond

   If such character was found, it is *replaced* by the null character '\0' and the pointer to the following character is stored in a static location for subsequent invocations.

   If str is a null pointer, the call is treated as a subsequent call to strtok: the function continues from where it left in previous invocation. The behavior is the same as if the previously stored pointer is passed as str. 

   #### Not Found

   If no such character was found, there are no tokens in `str` at all, and the function returns a null pointer.

   It's mean first not found will return full a string and second not found will return null pointer. And signify that the null pointer will not be returned until the function is called twice or more.

10. ### memset

   ```c
   void *memset( void *dest, int ch, size_t count );
   ```

11. ### memcpy

    ```c
    void* memcpy( void *dest, const void *src, size_t count );
    errno_t memcpy_s( void *restrict dest, rsize_t destsz,
                      const void *restrict src, rsize_t count );
    ```

12. ### memcmp && memncmp

    ```c
    int strcmp (const char *__s1, const char *__s2)
    ```

#### 		Return:

​			Negative value if `lhs`  appears before `rhs` in lexicographical order.

​			Zero if `lhs` and `rhs` compare equal, or if count is zero.

​			Positive value if `lhs` appears after `rhs` in lexicographical order.

###  