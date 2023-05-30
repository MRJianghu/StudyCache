# Array

​		Array name is const pointer.  You can't modify it's point memory

## 	Define:

```c
char arr[len];
char arr[] = {'a', 'b', 'c'};
```

## 	Initialize & Assignment

```c
//Initialize first then assignment

//Initialize
char arr[10] = {0};
//using memset
memset(arr, '\0', siezof(arr))
    
//Assignment
char arr[] = {'a', 'b', 'c', '\0'};
//memcpy
char arr[10];
memcpy(arr, "adawda" );
//scanf
scanf("%s", arr);
```



