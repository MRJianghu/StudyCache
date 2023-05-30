# Character Input/Output and Input Validation



## Buffer Input

### Introduce

Buffer Input, in which the characters you type are collected and storied in an area of temporary storage.Pressing Enter cause the block of characters you typed to made a avaliable to your programing.

### Buffer & Unbuffer input

Both buffer and unbuffer input have their uses. First, if you mistype, you can use your keyboard corrected features to fix your mistakes. On the other hand, is desirable for some interactive programs. In a game, for instance, you would like each command to take place as soon as you press key.

### Variety of Buffer(Input should be bufferd!)

#### Fully Buffer I/O

The buffer is flushed when it is full. Usually occurs with file input. The buffer size depends on the system. 

#### Line Buffer I/O

The buffer is flushed whenever a new line character show up. keyboard input normally line buffer, so that pressing Enter fluses the buffer.



# Terminating keyboard input

## File Stream and keyboard Input

### File in different system

Some store the file contents in one place and information about the file elsewhere. Some build a description of the file into the file itself. In dealing with text, some systems use a single newline character to mark the end of a line. Others might use the combination of the carriage return and linefeed characters to represent the end of a line. Some systems measure file sizes to the nearest byte; some measure in blocks of bytes.

The keyboard and the display device are treated as files opened automatically by every C program.

###  keyboard Input

keyboard input is represented by a stream called stdin, and output on the screen is represented by a stream called stdout.



## The End of File

### Mark by CTRLZ+ Z

Operating system usually use an embedded CTRL + Z character to mark the end of files. But, now the another approach is track the size of file. So modern text file may or may not have a embedded character CTRL+Z, but if it does, operating system will treat it as an end-of-file marker.

### Mark by track the file size



### Summarize

**C handles this variety of methods by having the getchar() function return a special value when the end of a file is reached, regardless of how the operating system actually detects the end of file(Mark by CTRLZ+ Z or Mark by strack the file size).** 

The important point is that EOF represents a value that signals the end of a file was detected; it is not a symbol actually found in the file.

The return value for getchar() when it detects an end of file is EOF. The **scanf()** function also returns EOF on detecting the end of a file.

### Note:

To use the program on keyboard input , you need a way to type the EOF character. No, you can't just type the letters E O F and can't just type -1. Instand, you have to find what you system require. Like CTRL + Z, CTEL + D an so on.

You never input ch