#String常用函数
判断  
 * boolean equals(Object obj):比较字符串的内容是否相同，严格区分大小写  
 * boolean equalsIgnoreCase(String str):比较字符串的内容是否相同，不考虑大小写  
 * boolean contains(String str):判断是否包含指定的小串  
 * boolean startsWith(String str):判断是否以指定的字符串开头  
 * boolean endsWith(String str):判断是否以指定的字符串结尾   

获取：  
 * int length():返回字符串的长度。字符的个数。  
 * char charAt(int index):返回字符串中指定位置的字符。  
 * int indexOf(int ch):返回指定字符在字符串中第一次出现的位置  
 * int indexOf(String str):返回指定字符串在字符串中第一次出现的位置  
 * int indexOf(int ch,int fromIndex):返回指定字符从指定位置开始在字符串中第一次出现的位置  
 * int indexOf(String str,int fromIndex):返回指定字符串从指定位置开始在字符串中第一次出现的位置  
 * String substring(int start):返回从指定位置开始到末尾的子串  
 * String substring(int start,int end):返回从指定位置开始到指定位置结束的子串----注意左包右不包  

转换:    
 * byte[] getBytes():把字符串转换为字节数组  
 * char[] toCharArray():把字符串转换为字符数组  
 * static String valueOf(char[] chs):把字符数组转成字符串  
 * static String valueOf(int i):把int类型的数据转成字符串  
 * 把任意类型转换为字符串的方法。  
 * String toLowerCase():把字符串转小写  
 * String toUpperCase():把字符串转大写  
 * String concat(String str):字符串的连接  

替换功能：
 * String replace(char old,char new)  
 * String replace(String old,String new)  

去除字符串两空格：  
 * String trim()  
