## 项目介绍

> 该项目为`Nuxt3`项目开发模板，其他`Nuxt3`项目可基于此开始开发

项目基本信息如下:

- 项目地址：[web_nuxt_tpl](https://gitlab.zfty.work/infrastructure/template/web_nuxt_tpl)
- 维护作者：2023010

## 快速启动

本项目使用 `node v18.16.0` 版本环境 `yarn`作为包管理工具

```
## 克隆项目
git clone ssh://git@gitlab.zfty.work:8022/infrastructure/template/web_nuxt_tpl.git

## 进入项目
cd web_nuxt_tpl

## 安装依赖
yarn install

## 启动项目
yarn dev
```

## 目录说明

```sh
web_nuxt_tpl
├─ .vscode
│  └─ settings.json          # 在本项目下覆盖开发者vscode的一些配置
├─ assets                    # 对tailwind 和 scss 都做一些全局的配置及变量
│  ├─ tailwind.css
│  └─ variables.scss
├─ components                # 项目组件
├─ composables               # 项目hooks函数
│  └─ useToast.ts
├─ layouts                   # 项目基础布局 default-layout
│  └─ default.vue
├─ middleware                # 中间件
│  ├─ amid.ts                # 具名中间件
│  └─ mid.global.ts          # 全局中间件
├─ pages                     # 项目下的所有页面, 一些示例页面可删除
│  ├─ auth.vue
│  ├─ component.vue
│  ├─ scss.vue
│  └─ tailwind.vue
├─ plugins                   # 项目插件 一些钩子函数
│  └─ vueApp.ts              # Vue App钩子
├─ public                    # 项目静态资源存放地址 例如图片等等
│  └─ favicon.ico
├─ server                    # 服务端一些配置
│  ├─ middleware             # 服务端中间件
│  │  └─ mid.ts
│  ├─ plugins                # 服务端插件 钩子函数 nitro
│  │  └─ nitroApp.ts
│  └─ tsconfig.json          # 服务端一些ts配置
├─ stores                    # 项目store位置
│  └─ global.ts              # 全局store
├─ .editorConfig             # 项目文件字符编码的统一配置
├─ .env                      # 环境变量
├─ .eslintrc                 # eslint配置
├─ .gitignore                # git提交忽略文件
├─ .nvmrc                    # node版本
├─ .prettierrc               # prettier格式化文件配置
├─ app.vue                   # 项目入口app.vue
├─ CHANGELOG.md
├─ global.d.ts               # 全局ts声明模块配置
├─ nitro.config.ts           # 配置nitro的跨域转发代理
├─ nuxt.config.ts            # 全局nuxt的配置
├─ package.json
├─ README.md
├─ tsconfig.json             # ts全局配置
└─ yarn.lock
```

