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
  * Bridge
    * InputStreamReader
    * OutputStreamWriter
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

## Chapter 05 Collection
* Arrays
  * java.util.Arrays
  * `Arrays.sort()`
  * `Arrays.fill(String[],String)`
  * `Array.hashCode(String)`
* Collection
  * `Set<E> //non-repeat`
    * `SortedSet<E>`
  * `List<E>`
  * `Quene<E>`
* Map
  * `HashMap<K,V>`
    ``` java
    HashMap<Integer,String> map = new HashMap<Integer,String>();
    map.put(0,"Hanyuu");
    String name = map.get(0);
    map.remove(0);
    Set keySet = map.keySet();
    Collection valueSet = map.values();
    Set entrySet = map.entrySet();
    ```
  * `SortedMap<K,V>`
* Iterator
* Seqential and Linear
* Use Array as Backend
* Varible Length
* Methods
  ``` java
  add(Object)
  add(int index,Object)
  remove(Object)
  get(int)
  set(int)
  indexOf(Objects)
  clear()
  Size()
  toArray()
  ```
* ArrayList
  * `ArrayList<String> list = new ArrayList<String>();`
  * `ArrayList<String> list = new ArrayList<String>(100);`
  * `list.ensureCapacity(1000)`
* LinkedList
  ``` java
  LinkdList<String> list = new LinkedList<String>();
  list.add("Hanyuu");
  Iterator<String> iterator = list.iterator();
  while(iterator.hasNext()){
    System.out.println(iterator.next());
  }
  ```
## Chapter 07 UI
  * java.jwt
  * javax.swing
  * `JFrame frame = new JFrame(String //title);`
    * `frame.getContentPane().add(BorderLayout.EAST,button);`
    * `frame.setSize(300,400);`
    * `frame.setVisible(true);`
    * `frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);`
    * `Container cp = frame.getContentPane();`
    * `cp.setLayout(new FloatLayout());`
    * `cp.add(new JPanel)();`
  * `JButton button = new JButton("Okey");`
  * `JComboBox`
  * `JCheckBox`
  * `JPanel`
    * `pnel.setLayout(new FLowLayout(FlowLayout.LEFT));`
  * `JPanel //container`
    * `JPanle = new JPanel();`
    * `panel.add(new JTextField("Hanyuu"));`
  * `JSplistPane`
  * `JScrollPane`
  * `Graphics`
  * `JLabel`
      * `getText();`
      * `setText();`
      * `setIcon();`
  * `JTextField`
  * `JCheckBox`
  * `JTextArea`
  * `JRadioButton`
  * 事件侦听
    * ActionLinstener
      ``` java
      public class Action implements ActionListener{
        public void actionPerformed(ActionEvent event){
          //TODO...
        }
      }
      JButton exp = new JButton();
      exp.addActionLintener(new Action());
      ```
## Chapter 08 Multi-thread
 1. `runnable` interface
    ``` java
    public class Task implements Runnable{
      public void run(){
        //TODO...
      }
    }
    public static void main(String[] args){
      Thread thread = new Thread(new Task(),"Thread name");
      thread.start();
    }
    ```
 2. Thread
   ``` java
   public class HanyuuThread extends Thread{
     public void run(){
       //TODO...
     }
   }
   public static void main(String[] args){
     HanyuuThread hanyuu = new HanyuuThread();
     hanyuu.setName("Hanyuu");
     hanyuu.statrt();
   }
   ```
   * `Thread.sleep(int)`
   * `String  Thread.currentThread().getName();`
   * `join`
   * `interrupt()`
   * `yield()`
  > yield意味着放手，放弃，投降。一个调用yield()方法的线程告 诉虚拟机它乐意让其他线程占用自己的位置。这表明该线程没 有在做一些紧急的事情。注意，这仅是一个暗示，并不能保证 不会产生任何影响。 \
    Yield告诉当前正在执行的线程把运行机会交给线程池中拥有相 同优先级的线程。\
    Yield不能保证使得当前正在运行的线程迅速转换到可运行的状态。\
    它仅能使一个线程从运行状态转到可运行状态，而不是等待或阻塞状态
   * `notify()`/`notifyAll()`
     * notifyAll() wakes all waiting thread, thus, all waiting thread turn to Ready
     * notify() only wakes one of waiting thread, others remain blocked
   * `sleep()`
     * java.lang.Thread`
   * `wait()`
     * `java.lang.Object`
     * Each object has a wait method, inherited from java.lang.Object
     * wait() method ask current thread to give up exclusive control
     * wait() method give other thread a chance to visit the object
     * wait() / wait(long timeout)
   *  wait() / notifyAll() / notify()
      *  The object must be locked before visit these methods
      *  They can be used in synchronized method of an object
      *  Or obj.wait() / obj.notifyAll() / obj.notify() in synchorized(obj){…}
      *  Otherwise: java.lang.IllegalMonitorStateException
   * `synchronized`
    ``` java
    public class Hanyuu{
      public synchronized void onlyOne(){
        //TODO...
      }
      public synchronized void threadSafty(){
        //TODO...
      }
    }
    ```
## Chapter 09 Java & XML
## Chapter 10 JDBC
* Record
* Field
* Table
* Entity
* Relations
* DataBase
* Primary key
* Foreign key
* Select
  * `SELECT nameA FROM tableA`
  * `SELECT nameA FROM tableA WHERE name > 2`
  * `SELECT nameA FROM tableA WHERE (name > 2 AND name < 10) OR name >300`
  * `SELECT * FROM tableA WHERE name IN ('Hanyuu','Inari')`
  * `SELECT * FROM tableA WHERE date BETWEEN 'Jan-01-2019' AND 'Jan-02-2019'`
  * `SELECT * FROM tableA WHERE name LIKE '%an%'`
  * `SELECT * FROM tableA ORDER BY name DESC/ASC`
  * `SELECT COUNT(DISTINCT name) FROM tableA`
* Insert
  * `INSERT INTO tableA (name,Date) VALUES ('Inari','Jan-01-2019')`
* Retireval
* Update
  * `UPDATE tableA SET date = 'Jan-01-2019' WEHERE name = 'Hanyuu'`
* Delete
  * `DELETE FROM tableA WHERE name = 'Inari'`
  ###### 你知道为什么SQL语句大家都选择大写嘛？（hhh）
  ``` java
  package SQL;
  import java.sql.*;
  import javax.sql.*;
  public class SQL {
  	public static void main(String[] args) {
  //		ResultSet rs;
  //		Statement statement;
  //		Connection connection;
  		Connection connection = null;
  		Statement statement = null;
  		ResultSet rs = null;
  		try {
        //注册驱动程序
  			Class.forName("com.mysql.cj.jdbc.Driver");
        //创建JDBC连接
  			String dbURL = "jdbc:mysql://localhost:3306/Hanyuu?user=Hanyuu&password=Hanyuu&useSSL=false&serverTimezone=GMT";
  			connection = DriverManager.getConnection(dbURL);
        //创建statement
  			String sqlQuery = "SELECT DISTINCT bookname FROM bookstore";
  			statement = connection.createStatement();
  			rs = statement.executeQuery(sqlQuery);
  			while (rs.next()) {
  				System.out.println(rs.getString("bookname"));
  			}
  			String nsqlQuery = "SELECT * FROM bookstore";
  			rs = statement.executeQuery(nsqlQuery);
        //执行查询语句
  			ResultSetMetaData rsmd = rs.getMetaData();
  			for (int i = 1; i <= rsmd.getColumnCount(); ++i) {
  				System.out.println(rsmd.getColumnName(i)+'\t');
  			}
  		} catch (ClassNotFoundException e) {
  			System.out.println("无驱动类");
  		} catch (SQLException e) {
  			e.printStackTrace();
  		} finally {
  			try {
  				rs.close();
  				statement.close();
  				connection.close();
  			} catch (Exception e) {
  				e.printStackTrace();
  			}
  		}
  	}
  }
* 构建Prepared statement
  ``` java
  String sql = "INSERT INTO tableA (id,name,sorce) VALUES (?,?,?)";
  PreparedStatement s =connection.prepareStatement(sql);
  //add a record
  s.setInt(1,0000);
  s.setString(2,"Hanyuu");
  s.setInt(3,60);
  s.addBatch();
  s.clearParameters();
  s.executeBatch();
  s.cleatBatch();
  ```
## Chapter 11 Java network Programming
* IP address
* IPv4
* IPv6
* IP
* Host name
* Domain Name
* DNS
``` java
try{
  //get InetAddress
  InetAddress iAddress = InetAddress.getLocalHost();
  //get local IP
  String IP = iAddress.getHostAddress().toString();
  //get local host name
  String hostName = iAddress.getHostName().toString();
  System.out.println("IP address"+IP);
  System.out.println("Host name"+hostName);
}
catch (UnknownHostException e){
  e.printStackTrace();
}catch(Exception e){
  e.printStackTrace();
}
```
* 通过主机名获取所有IP
``` java
import java.net.InetAddress;
import java.net.UnknownHostException;
import java.util.ArrayList;
import java.util.Iterator;

public class getLocal {
	public static void main(String[] args) {
		try {
			InetAddress ia=InetAddress.getLocalHost();
			System.out.println(ia.getHostAddress());
			System.out.println(ia.getAddress());
			System.out.println(ia.getHostName());

			String hostName=InetAddress.getLocalHost().getHostName();
			ArrayList<String> allIP=new ArrayList<String>();

			if (hostName.length()>0)
			{
				InetAddress[] addresses=InetAddress.getAllByName(hostName);
				for (int i=0;i<addresses.length;i++){
					allIP.add(addresses[i].getHostAddress().toString());
				}
			}
			for (Iterator iter=allIP.iterator();((Iterator) iter).hasNext();){
				System.out.println(iter.next().toString());
			}
		} catch (UnknownHostException e) {
			e.printStackTrace();
		}

	}
}

```
