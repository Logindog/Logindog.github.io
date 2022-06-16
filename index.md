# G7_Java_HomeWork

			  __ |__  | |  (_) |__ _ _ __ _ _ _ _  _ 	
			 / _` |/ /| |__| | '_ \\ '_/ _` | '_| || |	
			 \\__,/_/ |____|_|_.__/_| \\__,_|_|  \\_,	
			 |___/                              |__/		


## 项目介绍

这是一个基于 **Java** **MySQL** **Shell** 开发的图书管理系统，已经接入 **云端** 的MySQL数据库，可以随时调用修改。

## 项目功能

1.你可以在图书管理直接录入图书信息，以及更新图书内容等等运维管理。

2.基于Java编写，运行效率更高，省去繁琐的MySQL数据库语句添加。

3.数据存储在云端，可以有效防丢失。

## 项目人员

![S_DDY0OH9A~LBLX3ABXM6`Q.jpg](https://s2.loli.net/2022/06/16/a9jYKRrUxmhTnqC.jpg)

## Github源码

这个是我们小组的 [**Github仓库**](https://git.imaries.cf/Kmroiosn/Homework_LibraryManageSystem);

## 实现原理

通过 java 的 **JDBC** 的API调用MySQL实现用Java向MySQL数据库中录入数据。

## 项目开发平台支持

Eclipse Java, Oracle MySQL ，Debian Linux.

### Eclipse Java

主开发平台，使用Java编写主系统，提供主界面.

调用方法：**JDBC** 为主，并且使用了 for,if 等基本语法.

例如：

```java
public static Connection getInstance() {
	if (m_Connection == null) {
		try {
			FileReader fr = new FileReader(new File("DatabaseSettings.txt"));
			BufferedReader br = new BufferedReader(fr);
			if (!fr.ready() || !br.ready()) System.err.println("无法从DatabaseSettings.txt中获取数据库访问信息");
			
			String address  = br.readLine();
			String username = br.readLine();
			String passwd   = br.readLine();
					
			m_Connection = DriverManager.getConnection(address, username, passwd);
		} catch (IOException | SQLException e) {
			e.printStackTrace();
		}
		
	}
	return m_Connection;
}
//引用部分JDBC的连接源码
```

### Oracle MySQL

负责API接入兼调用存储数据.

调用方法: SQL语句为主，其中包含创建数据库，创建表，录入数据等SQL语句。

例如:

`CREATE DATABASE IF NOT EXISTS g7_library; //创建一个叫做g7_library的数据库` 

### Debian Linux

负责云端存储MySQL数据.

调用方法: 在Debian Linux的服务器环境使用SHELL语句安装MySQL，完成云端MySQL配置。

例如:

`sudo apt install mysql //在Debian类Linux中安装MySQL环境`

`mysql -h tencent.0330.cf -P 3306 -u niit -p root //连接到远程MySQL服务器`

或者使用由 **myPHPadmin** 提供的 [**GUI**](http://114.132.189.77:888/phpmyadmin_45eb48f3ff573c4a/) 进行连接.
