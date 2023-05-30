# JPEG

​	The jpeglib.h hav already defined the struct for image of jpeg. So you can get all of the picture imformation from the api form jpeglib.

​	The original images is composed of pixles and erery pixel has a read green and blue component.Each with a value from 0 to 255.And thr combination of these three values of r g and  b results in a color for a single pixel.

***Saied that images is composed of pixles and erery pixel has a R G B component***

​	The process of color sapce conversion takes these three r g and b values for ervery single pixel and calculates three new values luminance blue chrominance and red chrominance, abbreviated **Y,Cb and Cr.**

***Saide that jpeg stroed a image by Y Cb and Cr. And Y,Cb and Cr can calculated by the R G B***

​	Howerver, the next step called chrominence downsampling removers a considerable amount of date.The information that our eys are poor at perceiving the red and blue chrominence component images are shrunk to one quarter of the orginal size but the luminance remains the same. Then, with the rgb values being recalulated form luminance blue chrominance and red chrominants.



​	In a word, jpeg algorithm flow path:

​		1）色彩空间转换（Color Space Conversion"），将RGB转换为YUV色彩空间，YUV的数据更好处理 

​		2）色度缩减采样（Chromenance Downsampling），将蓝红色度层的“分辨率”变小，因为人眼对颜色不敏感 		3）离散余弦变换（Discrete Cosine Transform），找出人眼不敏感的高频信息 

​		4）量化（Quantization），删除人眼不敏感的高频信息 

​		5）游程编码与霍夫曼编码（Run-length Encoding & Huffman Encoding），通用数据压缩

​		6）重构图片