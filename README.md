# Whoothing 悟性

## 项目简介

该系统旨在为在家教育提供一个高效、方便、安全且完全可控的解决方案，以辅助孩子，学长以及家长们在学习中贯彻我们的基督化教育原理。同时也为监督者以及长者提供完整的权限审查和设置。系统设计注重以下核心功能：



1. **严格的权限划分**：

   不同用户角色（如学生、家长、学长、据点负责人等等）享有明确的权限范围，确保学习活动在清晰的规则下且不受干扰地进行。

2. **完整的权限控制与规则**：

   包括权限任命机制，账号注册，群组创建等等。

3. **效率**：

   尽可能简化每日报告，年表，课表等等的安排效率。

4. **分布式系统**：

   数据在云端以及各据点分布放置，一方面提高据点数据操作的容错，一方面可以提高数据的安全性。

5. **安全性**：

   所有的网络访问都将进行加密，且在数据库的设计上也体现这一点。另外，服务器(据点或云服务器)都将定时备份数据。

6. **Apple 的多平台支持**：

   支持 macOS, iOS, ipadOS。
   



## 系统架构

![网络部署](./diagrams/1.网络部署.png)



## 功能模块

### 系统功能

* **分布系统**
  * 据点内数据请求无需请求服务器，降低请求频次，也提高了访问速度。
  * 跨据点数据请求使用 P2P 技术，去中心化以降低延时。
* **统一的身份验证机制**

### 云端功能

- **门户网站**
  - 公开网站，展示公开信息，例如联系方式、培训计划、介绍 等等。
  
- **服务分发**：
  - 通过多个 网络服务 分布式部署，实现模块化设计。
- **远程存储与访问控制**：
  - 支持多设备数据同步。

### 本地功能
- **高效数据处理**：
  - 使用本地据点服务器处理高频、低延迟的请求。
  - 与云端同步和备份数据，保证一致与安全性。
- **内部服务支持**：
  - 提供局域网内的快速服务（如 TCP 传输和任务分发）。



## 部署说明

### 环境要求

- **云服务器环境**：
  - Ubuntu 24.04.1+
  - 4 vCPUs+
  - 8G RAM+
  - root 权限
- **据点服务器**
  - MacOS 或 Linux
  - 2 vCPUs+
  - 4G RAM+
  - root 权限
- **开发工具**：
  - **API 服务**：Node.js 16+
  - **客户端开发**：Swift 5+ / Objective-C (不推荐)
  - **数据库**：PostgreSQL16+, SQLite 3+
  - **反向代理**：Nginx 1.24+
  - **网站开发**：Nuxt, Vue, Express, Vapor



## 使用说明

### 快速启动
1. 克隆项目到本地：
   ```bash
   cd <你的项目文件夹>
   git clone https://github.com/SJJC-Team/Whoothing.git
   cd Whoothing
   ```


### **贡献指南**

 要对源文件作出修改时，请遵循以下约定：

* 创建您自己的分支，遵循分支名称格式，请确保您的分支版本号是最新的：
  * <该分支要使用的版本号>-developer-<您的名称>-<分支功能介绍>，
  * 如 "0.2.1-developer-clwang-init-project"
* 提交您的代码时，请在简介之前标注版本号，如 "V0.2.1.3 更新 README.md"，确保该版本号与您分支的版本号一致
* 禁止直接 push 或 merge 到 main 和 develop 分支以及任何不属于您的分支！若您完成了您的任务，请创建 pull request，由审核人将您的修改提交到主分支。
* 版本号规范中，"2.1.3.4"
  * 第一个数字为大版本号，表示一个发布版本，仅管理者可以创建。
  * 第二个数字为小版本号，通常表示一些功能的开发版本，仅管理者可以创建
  * 第三个数字为开发者分支版本号，表示开发者为了开发某个功能而创建的分支号，任何开发者均可创建，但请确保该版本号永远递增。
  * 第四个数字以及之后的数字均由开发者自行定义，完全由开发者控制，但请确保前 3 位版本号与您的分支号一致且其后的版本号递增。

如下：

![git约定](./diagrams/2.git约定.png)



## **许可证**

本项目采用 [Mozilla Public License Version 2.0](LICENSE) 开源。



## **联系方式**

* 开发者邮箱：inspiral@inspiral.site

* 项目主页：尚无
