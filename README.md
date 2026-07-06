# Vue 学生管理系统

这是一个基于 **Spring Boot + Vue 3** 的前后端分离学生管理系统，适合作为前端开发方向的练习项目和简历项目。项目包含登录认证、学生信息管理、用户管理、分页查询、表单校验等常见后台管理功能。

## 项目特点

- 前端使用 Vue 3、Vue Router、Axios、Element Plus、Vite。
- 后端使用 Spring Boot、Spring Security、JWT、Spring Data JPA、MySQL。
- 支持用户登录、注册、角色权限控制。
- 支持学生信息新增、查询、修改、删除。
- 支持学生列表分页展示。
- 已增加学生列表本地搜索功能，可按学号、姓名、年级、专业进行筛选。

## 技术栈

### 前端

- Vue 3
- Vue Router
- Pinia
- Element Plus
- Axios
- Vite

### 后端

- Spring Boot
- Spring Security + JWT
- Spring Data JPA
- MySQL
- Maven

## 项目结构

```text
.
├── src/                         # Spring Boot 后端源码
│   ├── main/java/               # Java 业务代码
│   └── main/resources/          # 配置文件和数据库脚本
├── student-management-ui/       # Vue 前端项目
│   ├── src/api/                 # 接口请求封装
│   ├── src/router/              # 路由配置
│   ├── src/views/               # 页面组件
│   └── package.json             # 前端依赖配置
├── pom.xml                      # 后端 Maven 配置
└── README.md
```

## 快速启动

### 1. 初始化数据库

创建 MySQL 数据库，并根据 `src/main/resources/db/init.sql` 初始化表结构。

```sql
CREATE DATABASE student_management;
```

### 2. 启动后端

修改 `src/main/resources/application.yml` 中的数据库账号和密码，然后执行：

```bash
mvn spring-boot:run
```

### 3. 启动前端

```bash
cd student-management-ui
npm install
npm run dev
```

## 主要接口

| 模块 | 方法 | 路径 | 说明 |
| --- | --- | --- | --- |
| 认证 | POST | `/api/auth/login` | 用户登录 |
| 认证 | POST | `/api/auth/register` | 用户注册 |
| 学生 | GET | `/api/students` | 获取学生列表 |
| 学生 | POST | `/api/students` | 新增学生 |
| 学生 | PUT | `/api/students/{id}` | 修改学生 |
| 学生 | DELETE | `/api/students/{id}` | 删除学生 |

## 本次改造点

在 `student-management-ui/src/views/student/List.vue` 中增加了学生列表搜索框，并使用 Vue `computed` 实现按学号、姓名、年级、专业的本地筛选，提升后台列表的查询体验。
