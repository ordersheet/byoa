## 详情见相关资料文件夹下内容，包含预览和设计的主要步骤









### 主要功能

####1 登录入口

####2 个人信息

####3 员工管理

####4 部门管理

####5 站内交流

####6 权限管理

####7 文件管理

####8 日程管理

####9 工作流程

### 主要技术

#### 1.SpringBoot

#### 2.缓存Redis

#### 3.持久层框架Mybatis

#### 4.工作流引擎Activity

#### 5.安全框架Shiro

#### 6.模板引擎Thymeleaf

#### 7.日志框架SLF4J

#### 8.数据库Mysql5.7

#### ....














**权限管理**使用RBAC的权限控制系统，使用角色作为系统权限的载体。将系统的权限先分配到角色中，管理者可在角色管理页面增加、删除、修改角色信息。角色信息包括角色名称、角色权限等（详见角色表SYS_ROLE）。其中系统权限存储在系统资源表中，资源信息包括：资源名称、资源类型、资源URL，资源访问权限标识等（详见系统资源表SYS_RESOURCES）。在员工管理模块中将角色分配给用户，用户自动拥有该角色的系统权限。系统权限体现在左侧菜单、操作按钮上，无相应权限则不显示操作菜单，页面上不显示相应的操作按钮。**每个不用角色登入系统后左侧菜单会有所不同**。



**乐观锁**：乐观锁并不是数据库自带的锁，需要在程序中实现，乐观锁在操作数据库时，想法很乐观，认为此次的操作数据竞争（data
race）概率很小，尽可能往下进行，各事务在不产生锁的情况下影响属于当前事务的数据，直至提交时才会校验在本事务读取数据后，该数据是否被其他事务修改产生了过期数据。这种方式在偶尔回滚事务的环境中，吞吐量远比其他并发控制要好。乐观锁检查过期数据的方式有两种，第一是在数据库加入版本号字段，生成数据时指定一个版本号，每次要更新数据前，需要查询一次当前版本号，更新操作需比对版本号后更新版本号。第二种是使用时间戳，方法与第一种类似。**此系统中采用了版本号作并发控制**。

## .........

