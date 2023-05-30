<h1 align = "center">Pointer to an Array | Array Pointer
</h1>



Author: HuJiang

Date: 2023年05月25日22:38:34

1. ## Pointer to an Array

   ### 	Farmat:

   ```c
   //defined
   char (*p)[len];
   
   //dynamic memory
   char (*p)[] = (char (*)[]) malloc (sizeof(char (*)[len]) * row);
   ```

   ​	P is a pointer which is point a array. 

   ​	It's characteristic is  p is always point the arr head adress. When you execute p += 1，p will add len step. 

   ### 	Usage scene

   ​			2D array as a fuction argument		

1. ### Array of Point

   ### 	Farmat:

   ```c
   char* p[row];
   char** p;
   
   void arrOfPointer()
   {
       char* *arr = (char **) malloc(sizeof (char *) * 10);
       int len = 10;
       for (int i = 0; i < len; ++i) {
           arr[i] = (char *) malloc(sizeof (char ) * 10);
       }
       
       for (int i = 0; i < len; ++i) {
           free(arr[i]);
       }
       free(arr);
   }
   ```

1. Array as a function argument

   ```c
   //Pointer to array
   * void fun(int arr[3][4], int row, int col)
    * void fun(int arr[][4], int row, int col)
    * void fun(int (*arr)[4], int row, int col) //recommend
    
    //Array of pointer
    * void fun(int **arr, int row, int col)
    * void fun(int *arr[], int row, int col)
   ```

   



