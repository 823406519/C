# stdio.h
[toc]
 
## printf
        int printf(const char *format, ...)
1. 描述：发送format参数指定的字符串输出到stdout
2. 参数：format指定输出的字符串，可以选择添加格式标签(format tag), 格式标签原型是

        %[flags][width][.precison][length]specifier

    详细点击 [printf格式标签][format tag]
3. 返回值： 返回写入的字符数量

## fprintf
        int fprintf(FILE *stream, const char *format, ...)
1. 描述： 将format的格式化输出匹对参数输出到stream指定的文件
2. 参数： 参数stream是指定文件，参数format指向格式字符串，format的格式标签可以参考[printf格式标签][format tag]

## scanf
        int scanf(const char *format, ...)
1. 描述：从stdin读取字符，按照format指定的格式字符串，存储到对应的参数
2. 参数：format指定输入的字符串，可以选择添加格式标签(format tag), 格式标签原型是

        %[*][width][length]specifier

    详细点击 [scanf格式标签][format tag2]
3. 返回值：返回读取成功的参数数量

## fscanf
        int fscanf(FILE *stream, const char *format, ...)
1. 描述： 根据format指定字符串的格式，从stream指定的文件中读取输出到指定参数中
2. 参数： 参数stream指向文件对象，format指向格式字符串, format的格式标签可以参考 [scanf格式标签][format tag2]
3. 返回： 返回成功读取的参数项数量

## getchar
         int getchar(void)
1. 描述：从stdin中获取一个字符
2. 返回值：返回读取字符的int类型, 文件结尾或者错误返回EOF

## fgetc
         int fgetc(FILE *stream)
1. 描述：从指定stream中读取一个字符, 之后流的位置指示器会移动一位
2. 参数：参数stream指向文件对象
3. 返回值：返回读取字符的int类型，文件结尾或者错误返回EOF

## putchar
        int putchar(int char)
1. 描述：将参数char指定的字符，输出到stdout
2. 参数：参数char指定一个字符
3. 返回值：返回输出字符的int类型，错误返回EOF

## fputc
         int fputc(int char, FILE *stream)
1.  描述：将char指定的字符，输入到stream指定的文件
2.  参数：参数char是字符的int类型， stream是指定文件对象
3.  返回值：返回写入的字符int类型，如果错误返回EOF

## gets
        char *gets(char *str)
1. 描述：从stdin读取字符串，存储到str指定字符串
2. 参数：str指向一个字符串 
3. 返回值：返回输入字符串的指针


## fgets
        char *fgets(char *str, int n, FILE *stream) 
1. 描述：从stream指定文件流读取n-1个字符, 存储到str指定数组中
2. 参数：参数stream指向文件对象，参数str指向数组，n是读取字符的最大数目（包括'\0'字符）
3. 返回值：返回指向读取的字符串的指针，EOF或者出现错误返回null

## puts
        int puts(const char *str)
1. 描述：将str指定的字符串，输出到stdout中
2. 参数： str指向一个字符串
3. 返回值： 成功返回非负数，错误返回EOF

## fputs
        int fputs(const char *str, FILE *stream)
1. 描述：将str指定的字符串，输出到stream指定的文件
2. 参数：参数str指向字符串，参数stream指向文件对象
3. 返回：成功返回非负值，失败返回EOF


## fopen
        FILE *fopen(const char *fileName, const char *mode)
1. 描述：根据参数mode指定的模式，打开fileName指定的文件
2. 参数：fileName指向包含文件名的字符串，modez指向包含文件访问模式的字符串。
    文件访问模式分类 | 描述
    -|-
    "r"             | 文件必须存在, 以”**只读**“模式打开
    "w"             | 创建一个空文件进行**写操作**，如果文件已经存在，将原有文件内容清除为空内容
    "a"             | 打开文件，在原有文件末尾继续**写入**，如果不存在文件，会自动创建空文件
    "r+"            | 打开文件进行**读和写**，**文件必须存在**
    "w+"            | 创建空文件进行**读和写**，如果文件已经存在，将原有文件内容清除为空内容
    "a+"            | 在原文件基础上打开文件进行**读和写**，如果文件不存在，创建一个空文件
3. 返回值：返回FILE指针, 有错误则返回NULL

## fclose
        int fclose(FILE *stream)
1. 描述：关闭文件流，文件缓冲区刷新(flush)
2. 参数：参数stream指向文件对象
3. 返回值：成功返回0， 失败返回EOF

## rewind
        void rewind(FILE *stream)
1. 描述: 对于stream指定的文件，将文件位置设置为文件开头
2. 参数：参数stream指向文件对象

[format tag]: http://note.youdao.com/noteshare?id=1a707b06cb6a2d459c5f061622a81767&sub=3C545D758E0843DD888DB0C01EF07093
[format tag2]: http://note.youdao.com/noteshare?id=ad9ee953bbe7d1c857999f951375246f&sub=2D7B2BE023A547EABF765CFD4C9C4DF6

