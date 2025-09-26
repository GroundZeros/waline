# iFlow 上下文：Waline 项目

## 项目概述

Waline 是一个支持后端的简单评论系统。它具有以下特点：

- 快速
- **真正**安全
- 支持完整的 Markdown 语法
- 简单轻量
- 免费部署！
- 支持多种部署和存储服务，至少有 243 种部署选择！

### 核心技术栈

- **前端 (Client)**: Vue 3, TypeScript
- **后端 (Server)**: Node.js, ThinkJS, Koa
- **API**: 用于前后端通信的专用包
- **构建工具**: pnpm, Rollup, Vite
- **包管理器**: pnpm

### 主要包 (Packages)

该项目是一个使用 pnpm 工作区管理的 monorepo，包含以下主要包：

1. **`@waline/client` (`packages/client`)**: Waline 的前端客户端库，提供评论组件和页面浏览量统计功能。
2. **`@waline/vercel` (`packages/server`)**: Waline 的后端服务，可部署在 Vercel 等平台上，负责处理评论数据、用户认证、通知等。
3. **`@waline/api` (`packages/api`)**: 客户端与服务端通信的 API 封装。
4. **`admin` (`packages/admin`)**: Waline 的管理后台界面。
5. **`cloudbase` (`packages/cloudbase`)**: 针对腾讯云 CloudBase 的部署支持。
6. **`hexo-next` (`packages/hexo-next`)**: 为 Hexo 博客框架 Next 主题提供的 Waline 插件。

## 构建与运行

### 前置条件

- Node.js (版本 >= 18，服务端建议 >= 20)
- pnpm (推荐使用 `corepack enable pnpm` 启用)

### 常用命令

- **安装依赖**: `pnpm install`
- **开发模式**:
  - 启动客户端开发服务器: `pnpm client:dev`
  - 启动服务端开发服务器: `pnpm server:dev`
  - 启动管理后台开发服务器: `pnpm admin:dev`
- **构建**:
  - 构建所有包: `pnpm build`
  - 仅构建客户端: `pnpm client:build`
  - 仅构建 API 包: `pnpm api:build`
  - 仅构建管理后台: `pnpm admin:build`
- **文档**:
  - 启动文档开发服务器: `pnpm docs:dev`
  - 构建文档: `pnpm docs:build`
- **测试**: `pnpm test`
- **代码检查与格式化**:
  - 运行所有检查: `pnpm lint`
  - 运行 ESLint: `pnpm lint:eslint`
  - 运行 Prettier: `pnpm lint:prettier`
  - 运行 Stylelint: `pnpm lint:stylelint`
  - 检查 Markdown: `pnpm lint:md`

## 开发约定

- 使用 **pnpm** 作为包管理器。
- 使用 **ESLint**, **Prettier**, **Stylelint** 和 **markdownlint** 进行代码质量控制和格式化。
- 使用 **Husky** 和 **nano-staged** 进行 Git 钩子管理，确保提交前代码符合规范。
- 使用 **Conventional Commits** 规范提交信息。
- 使用 **TypeScript** 进行类型检查。
- 使用 **Rollup** 和 **Vite** 进行构建和打包。
