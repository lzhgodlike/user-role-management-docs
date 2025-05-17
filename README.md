# 用户角色管理系统文档

这是用户角色管理系统的主要文档仓库，包含系统架构、部署指南和技术文档。

## 相关仓库

* [前端仓库](https://github.com/lzhgodlike/user-role-management-frontend)
* [后端仓库](https://github.com/lzhgodlike/user-role-management-backend)

## 项目概述

这是一个基于Spring Boot和Vue 3的全栈用户角色管理系统，包含前后端分离架构。系统实现了用户认证(登录/注册)和用户角色管理的完整功能，适合作为Web开发学习示例或小型项目的权限管理模块。

## 系统架构

系统采用前后端分离架构：

```
┌─────────────┐       ┌─────────────┐      ┌─────────────┐
│  Vue 3前端  │  <──> │ Spring Boot │ <──> │ MySQL数据库  │
│  (前端展示)  │       │  (后端API)  │      │ (数据存储)   │
└─────────────┘       └─────────────┘      └─────────────┘
```

### 前端 (Vue 3 + Vite)
- 提供用户界面
- 处理用户交互
- 通过API与后端通信
- 使用Element Plus作为UI框架

### 后端 (Spring Boot)
- 提供RESTful API
- 处理业务逻辑
- 管理数据库交互
- 实现安全认证

### 数据库 (MySQL)
- 存储用户和角色数据
- 通过JPA自动创建表结构

## 功能模块

### 1. 用户认证模块
- 用户注册
- 用户登录
- 简单的token认证

### 2. 用户角色管理模块
- 角色列表展示
- 角色搜索
- 角色创建
- 角色编辑
- 角色状态切换
- 角色删除

## 项目部署

### 部署架构图
```
                ┌─────────────┐
                │   Nginx     │
                │ 静态资源服务器 │
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
  ┌────────────>│   Vue 3     │
  │             │  前端应用    │
  │             └──────┬──────┘
  │                    │
  │                    ▼
┌─┴───────────┐  ┌─────────────┐  ┌─────────────┐
│ 用户浏览器   │  │ Spring Boot │  │   MySQL     │
│ User Browser│<─>│  后端API    │<─>│  数据库     │
└─────────────┘  └─────────────┘  └─────────────┘
```

### 快速启动指南

1. 克隆前后端仓库
```bash
git clone https://github.com/lzhgodlike/user-role-management-frontend.git
git clone https://github.com/lzhgodlike/user-role-management-backend.git
```

2. 启动后端服务
```bash
cd user-role-management-backend
mvn spring-boot:run
```

3. 启动前端服务
```bash
cd user-role-management-frontend
npm install
npm run dev
```

4. 访问应用
- 前端开发服务器: http://localhost:5173
- 后端API: http://localhost:8080

## 技术选型理由

### 前端
- Vue 3: 渐进式框架，易学易用，性能优秀
- Vite: 极速的开发构建工具，热更新快速
- Element Plus: 完善的组件库，提高开发效率
- Pinia: 轻量级状态管理，替代Vuex的新方案

### 后端
- Spring Boot: 简化Spring应用开发，微服务首选框架
- Spring Data JPA: 简化数据访问层，减少样板代码
- MySQL: 稳定可靠的关系型数据库

## 后续功能规划

1. 增强安全性
   - 实现JWT认证
   - 密码加密存储
   - RBAC权限控制

2. 功能扩展
   - 用户详情管理
   - 操作日志记录
   - 多级角色支持

3. 性能优化
   - Redis缓存集成
   - 数据库索引优化

## 贡献指南

欢迎贡献代码或提交问题，请遵循以下流程：

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/amazing-feature`)
3. 提交更改 (`git commit -m 'Add amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 创建Pull Request

## 许可证

本项目使用 MIT 许可证。

MIT许可证是一个宽松的软件许可证，它基本上允许任何人以任何方式使用您的代码，只要他们保留版权声明和许可证文本。这种许可证非常适合希望自由分享但同时希望获得基本归属的项目。

### MIT许可证要点：
- 可以自由使用、复制、修改、合并、发布、分发、再许可和/或出售软件的副本
- 唯一的条件是在所有副本或重要部分的软件中都必须包含上述版权声明和本许可声明
