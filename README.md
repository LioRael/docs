# Zephyrion 插件文档

Zephyrion 是一个基于 TabooLib 框架的 Minecraft Bukkit 插件，提供了工作空间 (Workspace) 和保险库 (Vault) 的管理系统，允许玩家存储和管理物品。

## 文档目录

### 用户文档

- [安装与配置](./[installation.md]\(http://installation.md\)) - 插件安装、数据库配置、缓存配置
- [命令与权限](./[commands.md]\(http://commands.md\)) - 所有命令及对应权限说明
- [用户使用指南](./guide/[README.md]\(http://README.md\)) - 详细功能使用教程
  - [快速入门](./guide/[getting-started.md]\(http://getting-started.md\)) - 基础操作与界面介绍
  - [工作空间管理](./guide/[workspace.md]\(http://workspace.md\)) - 创建、管理工作空间与成员
  - [保险库操作](./guide/[vault.md]\(http://vault.md\)) - 物品存储、搜索与容量管理
  - [自动拾取系统](./guide/[auto-pickup.md]\(http://auto-pickup.md\)) - 自动拾取规则配置
  - [工具自动替换](./guide/[auto-replace.md]\(http://auto-replace.md\)) - 工具损坏自动替换功能
  - [配额系统](./guide/[quota.md]\(http://quota.md\)) - 配额说明与管理
  - [常见问题](./guide/[faq.md]\(http://faq.md\)) - 问题解答与故障排除

### API 开发文档

- [API 开发入门](./api/[README.md]\(http://README.md\)) - API 文档索引
- [核心 API](./api/[core-api.md]\(http://core-api.md\)) - ZephyrionAPI 详细说明
- [事件系统](./api/[events.md]\(http://events.md\)) - 自定义事件监听
- [数据模型](./api/[models.md]\(http://models.md\)) - Workspace、Vault、Item 等数据结构

## 核心概念

### 工作空间 (Workspace)

工作空间是物品存储的顶级容器，有三种类型：

| 类型 | 说明 |

|------|------|

| PUBLIC | 公共工作空间，成员可查看和使用其中的保险库 |

| PRIVATE | 私有工作空间，仅创建者可访问 |

| INDEPENDENT | 独立工作空间，每个玩家拥有独立的物品存储 |

### 保险库 (Vault)

保险库归属于工作空间，用于存储物品。每个保险库按页面和槽位组织（每页 36 个槽位），支持容量扩展和物品搜索。

### 配额系统 (Quotas)

每个玩家拥有独立的配额数据，用于限制可创建的工作空间数量和总存储容量。

## 技术栈

- **语言**: Kotlin 1.9.0
- **JVM 目标**: Java 8
- **框架**: TabooLib 6.2.4
- **数据库**: MySQL / SQLite
- **缓存**: Memory / Redis

## 快速开始

1. 将插件放入 `plugins` 目录
2. 启动服务器生成配置文件
3. 编辑 `plugins/Zephyrion/settings.yml` 配置数据库
4. 重启服务器或执行 `/zephyrion reload`
5. 使用 `/ze open` 打开工作空间界面