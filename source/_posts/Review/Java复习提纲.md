---
title: Java 复习提纲
date: 2019-01-10 00:00:00
tags: Java
---
* 垃圾回收 `System.gc()`
## Chapter 01
* 数据类型

类型|容量（bit）|范围|包装器
:-|:-|:-|:-
boolean|1|true\false|Boolean
char|16|Unicode|Character
byte|8|$[-128,127]$|Byte
short|16|$[-2^{15},2^{15}-1]$|Short
int|32|$[-2^{31},2^{31}-1]$|Integer
Long|64|$[-2^{63},2^{63}-1]$|Long
float|32|$3.4*10^{38}$|Long
double|64|$1.7*10^{308}$|Double
void|-|-|Void
* 数据类型转换`int a = (int)3.14159`
* Package
* Import
* Class
* Field
* Method
* Object
* Constract and Initialization
* Access Control
## Chapter 02 OOP
* Object
* Class
* Abstraction
* Inheritance
* Polymorphism
* `finalilze();`
* `Abstraction`
* `interface`
* `implements`
## Chapter 03 Exception
## Chapter 04 Java I/O
``` java
	File file = new File("filePath/fileName");
	System.out.println(file.exists());
	System.out.println(file.isFile());
	File[] files = file.listFlies(filter);
	System.out.println(files.length);
	Arrays.sort(files,comparator);
```
* Stream
  * Byte stream
    * java.io.InputStream
      * `int read()	//read a byte`
    * java.io.OutputStream
      * `void write(int b)`
      * `void write(byte[] b)`
	* FileInputStream, FileOutputStream
	* PipedInputStream, PipedOutputStream
	* ByteArrayInputStream, ByteArrayOutputStream
	* BufferedInputStream, BufferedOutputStream
	* ObjectInputStreamm ObjectOutputStream
  * Character stream
    * java.io.Reader
      * `int read()	//read a char`
    * java.io.Writer
      * `void write(int b)`
      * `void write(char[] c)`
  * FileReader, FileWriter
  * PipedReader, PipedWriter
  * BufferedReader, BufferedWriter
  * InpputStreamReader, OutputStreamWriter
* FileInputStream
  * ``` java
  	FileInputStream fis = FileInputStream(file);
	  int  res = fis.read();	//IOException
	  fis.available();	//是否可用
	  fis.close();
	```
* FileOutputStream
  * ``` java
  	file.createNewFile()
	fos.write(2);
	fos.write('a');
	```
* FileReader
* FileWriter
  * ```java
    FileWriter w = new FileWriter(new File("a.txt"),true);
	w.write("Hanyuu".toCharArray());
	w.flush();
  	```
* InputStreamReader
* OutputStreamReader
* PrintStream
* DataInputStream, DataOutputStream
* PrintWriter
* Scanner
  * java.util.Scanner
* BufferedInputStream, BufferedOutputStream
  * `BufferedInputStream bufferedInput = new BufferedInputStream(new FileInputStream(filename));`
  * ``` java
	public void testBufferedInput() {
    try {
        /**
         * 建立输入流 BufferedInputStream, 缓冲区大小为8
         * buffer.txt内容为
         * abcdefghij
         */
        InputStream in = new BufferedInputStream(new FileInputStream(new File("buff.txt")), 8);
        /*从字节流中读取5个字节*/
        byte [] tmp = new byte[5];
        in.read(tmp, 0, 5);
        System.out.println("字节流的前5个字节为: " + new String(tmp));
        /*标记测试*/
        in.mark(6);
        /*读取5个字节*/
        in.read(tmp, 0, 5);
        System.out.println("字节流中第6到10个字节为: " +  new String(tmp));
        /*reset*/
        in.reset();
        System.out.printf("reset后读取的第一个字节为: %c" , in.read());
    } catch (Exception e) {
        e.printStackTrace();
    }
	}
	```
  * InputStreamReader
  * OutputStreamReader
  * System.in
  * System.out
  * System.err
  * DataOutputStream
  * DataInputStream
