<h1 align = "center">function argument</h1>

1. ## Array

​			There are three ways to pass an array as a function argument

```C
void display_array(int arr[], int size) ;
void display_array(int arr[10], int size) ; //10 is useless 
void display_array(int *arr, int size) ;
```

​			For character array, it's not necessary to defined `size` argument, becase array usually ending by '\0'.