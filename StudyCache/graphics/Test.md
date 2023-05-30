# TEST

​	JPEG不是直接通过RGB来显示图片的，而是把RGB变换成Y,Cb,Cr，通过Y,Cb,Cr来显示定义一个像素。关于JPEG的压缩原理，已经在[Jpeg](/home/jhu/myWork/StudyCache/graphics/Jpeg.md) 和 [傅里叶变换](/home/jhu/myWork/StudyCache/高等数学/傅里叶变换.md)中体现了。

​	图像由很多个像素块构成，而一个像素块可以由(R,G,B)这三元组来描述。图片的大小决定了像素块的数量，既像素数 = 长度 * 宽。

​	在Linux系统中，在终端上可以使用一下格式改名文本的颜色：

```c
// 设置前景颜色
printf("\033[30m"); // 黑色
printf("\033[31m"); // 红色
printf("\033[32m"); // 绿色
printf("\033[33m"); // 黄色
printf("\033[34m"); // 蓝色
printf("\033[35m"); // 紫色
printf("\033[36m"); // 青色
printf("\033[37m"); // 白色

// 设置背景颜色
printf("\033[40m"); // 黑色
printf("\033[41m"); // 红色
printf("\033[42m"); // 绿色
printf("\033[43m"); // 黄色
printf("\033[44m"); // 蓝色
printf("\033[45m"); // 紫色
printf("\033[46m"); // 青色
printf("\033[47m"); // 白色

// 还原颜色
printf("\033[0m");

//输出RGB颜色
printf("\033[48;2;%d;%d;%dm", R, G, B);
```

从而，可以在终端中输入RGB。

```c
void
show_rgb(unsigned char *buf, int width, int height) 
{
    int channels = 3;
    int row_stride = width * channels;
    for (int y = 0; y < height; y+=1) {
        for (int x = 0; x < width; x+=1) {
            printf("\033[48;2;%d;%d;%dm  ", buf[y * row_stride + x * channels + 0],
                   buf[y * row_stride + x * channels + 1],
                   buf[y * row_stride + x * channels + 2]);
        }
        printf("\n");
    }
}
```

