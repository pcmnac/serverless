<!--
title: Serverless - Tencent SCF - Components 概述
menuText: Components 概述
layout: Doc
menuItems:
  - {menuText: 基础 Components , path: /framework/docs/providers/tencent/components/basic-components}
  - {menuText: Components 最佳实践, path: /framework/docs/providers/tencent/components/high-level-components}
-->

Serverless Components 是支持多个云资源编排和组织的场景化解决方案，主要基于客户的具体场景，如 Express 框架支持、网站部署等。Serverless Components 可以有效简化云资源的配置和管理，将网关、COS 和 CAM 等产品联动起来，让客户更多关注场景和业务。

## 优势特性

**Serverless Components** 是 **[Serverless Framework](https://github.com/serverless/serverless/blob/master/README_CN.md)** 重磅推出的基础设置编排能力，支持开发者通过 **Serverless Components** 构建，组合并部署你的 Serverless 应用。

- - [x] **快速部署 -** Components 支持极速部署 Serverless 架构和应用
- - [x] **全面覆盖 -** 既能支持基础设施的 Components，也可以支持更高维度的，场景级别的 Components。
- - [x] **轻松复用 -** 你构建的每个 Component 都可复用，并且对外发布后，也可以支持他人使用。
- - [x] **灵活组合 -** 可以通过 YAML 或者 Javascript 灵活组合不同的 Components。

下面通过一个 Serverless Framework 使用 Components 的例子，可以看出 Component 多么易用：

```yaml
# serverless.yml
name: website

website:
  component: '@serverless/tencent-website'
  inputs:
    code:
      src: ./src
      # hook: npm run build
      # domain: www.serverlesscomponents.com
```

## 快速开始

通过 NPM 安装 [Serverless Framework](https://www.github.com/serverless/serverless) ：

```console
$ npm i -g serverless
```

**确保你使用的是 Serverless Framework 1.49 及以上的版本**。更早的版本无法支持 Serverless Components Beta。

之后，通过 `create --template-url` 命令安装一个 [Serverless Components 模板](./templates)，模板中会包含了 Componenets 及示例代码，可以让你更快的了解 Component。

以下是一些常用的用例模板：

#### [部署 Hexo 静态博客](https://github.com/serverless/components/tree/master/templates/tencent-hexo-blog)

通过 Serverless Website 组件快速构建一个 Serverless Hexo 站点

```shell
serverless create --template-url https://github.com/serverless/components/tree/master/templates/tencent-hexo-blog
```

#### [快速构建 REST API](https://github.com/serverless/components/tree/master/templates/tencent-python-rest-api)

通过 Serverless SCF 组件快速构建一个 REST API 应用，实现 GET/PUT 操作。

```shell
serverless create --template-url https://github.com/serverless/components/tree/master/templates/tencent-python-rest-api
```

#### [部署 Serverless 全栈 WEB 应用（React.js）](https://github.com/serverless/components/tree/master/templates/tencent-fullstack-react-application)

本示例以 React 为前端，Express 框架作为后端，通过多个 Serverless Components 部署 Serverless 全栈应用程序。

```shell
serverless create --template-url https://github.com/serverless/components/tree/master/templates/tencent-fullstack-react-application
```

#### [部署 Serverless 全栈 WEB 应用（Vue.js）](https://github.com/serverless/components/tree/master/templates/tencent-fullstack-vue-application)

本示例以 Vue 为前端，Express 框架作为后端，通过多个 Serverless Components 部署 Serverless 全栈应用程序。

```shell
serverless create --template-url https://github.com/serverless/components/tree/master/templates/tencent-fullstack-vue-application
```

#### [部署其他模板](./templates)

在这里查看所有预设的 [Components 模板](./templates)，你可以通过这些模板方便的部署*REST API*， 网站, *定时任务*等多种场景。每个模板都提供了清晰的 `README.md` 来说明怎样使用。

#### Serverless Components 列表

如下所示，当前 Serverless Components 支持丰富的多语言开发框架和应用：

[![Serverless Components Tencent](https://img.serverlesscloud.cn/20191213/1576236739852-Component%20Gallery.png)](https://github.com/serverless-components/)

基础组件：

- [@serverless/tencent-apigateway](https://github.com/serverless-components/tencent-apigateway) - 腾讯云 API 网关组件
- [@serverless/tencent-cos](https://github.com/serverless-components/tencent-cos) - 腾讯云对象存储组件
- [@serverless/tencent-scf](https://github.com/serverless-components/tencent-scf) - 腾讯云云函数组件
- [@serverless/tencent-cdn](https://github.com/serverless-components/tencent-cdn) - 腾讯云 CDN 组件
- [@serverless/tencent-cam-role](https://github.com/serverless-components/tencent-cam-role) - 腾讯云 CAM 角色组件
- [@serverless/tencent-cam-policy](https://github.com/serverless-components/tencent-cam-policy) - 腾讯云 CAM 策略组件

高阶组件：

- [@serverless/tencent-express](https://github.com/serverless-components/tencent-express) - 快速部署基于 Express.js 的后端服务到腾讯云函数的组件
- [@serverless/tencent-egg](https://github.com/serverless-components/tencent-egg) - 快速部署基于 Egg.js 的后端服务到腾讯云函数的组件
- [@serverless/tencent-koa](https://github.com/serverless-components/tencent-koa) - 快速部署基于 Koa.js 的后端服务到腾讯云函数的组件
- [@serverless/tencent-flask](https://github.com/serverless-components/tencent-flask) - 腾讯云 Python Flask RESTful API 组件
- [@serverless/tencent-laravel](https://github.com/serverless-components/tencent-laravel) - 腾讯云 PHP Laravel RESTful API 组件（任何支持 WSGI 的 Python 服务端框架都可以基于该组件进行部署，例如 Falcon 框架等。）
- [@serverless/tencent-website](https://github.com/serverless-components/tencent-website) - 快速部署静态网站到腾讯云的组件

第三方贡献：

- [@twn39/tencent-fastify](https://github.com/twn39/tencent-fastify) - 快速部署基于 fastify.js 的后端服务到腾讯云函数的组件
- [@twn39/tencent-php-slim](https://github.com/twn39/tencent-php-slim) - 快速部署基于 Slim PHP 微框架的后端服务到腾讯云函数的组件