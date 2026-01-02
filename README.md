# 智慧物流管理系统

数据库实验期末大作业

基于SQL Server + Node.js + Vue3 的智慧物流管理系统，负责管理物流车队、配送订单与报表等信息。



## 创建数据库

在SQL Server 中执行`物流系统SQLServer脚本.sql`即可。

此外，你还需要创建一个用户来管理这个数据库，你可以使用以下脚本来创建用户并授予权限。

```sql
USE [master]
GO

CREATE LOGIN [logistics_user] 
WITH PASSWORD = 'admin123',
     DEFAULT_DATABASE = [LogisticsDB],  
     CHECK_EXPIRATION = OFF,           
     CHECK_POLICY = OFF           
GO

USE [LogisticsDB]
GO

CREATE USER [logistics_user] FOR LOGIN [logistics_user]
GO

ALTER ROLE [db_owner] ADD MEMBER [logistics_user]
GO

PRINT '用户创建成功，已授予 LogisticsDB 数据库的所有权限'
```

你也可以通过 `backend/database.js` 来自定义登录名。



## 运行

### 1. 安装 Node.js

参考[Node.js官网](https://nodejs.org/zh-cn)

### 2. 安装项目依赖

```bash
cd backend
npm install
```

### 3. 启动服务器

```bash
npm run start
```

### 4. 访问页面

浏览器中访问 http://localhost:8080 即可。



## 开发者模式下运行

需要启动两个终端，前后端各一个。

### 1. 后端

```bash
cd backend
npm install
npm run dev-server
```

### 2. 前端

```bash
cd frontend
npm install
npm run dev-web
```

### 3. 打开页面

浏览器中访问 http://localhost:8000 即可。



## 前端代码打包和预览

```bash
cd frontend
npm run build
npm run preview
```

