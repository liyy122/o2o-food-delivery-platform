# 管理端前端源码（Vue 2 + TypeScript + Element UI）

这是管理端的**可编辑源码**，构建产物已经放在上一级的 `frontend/admin/`，直接用 Nginx 托管就能跑。
想改页面、样式或接口地址时，改这里的代码，重新构建后把 `dist/` 覆盖到 `frontend/admin/` 即可。

## 环境

- Node.js 16（推荐）或 14；不要用 18+，vue-cli 3 在 Node 18 上可能报 OpenSSL 错误
- npm 6+

## 本地开发

```bash
cd frontend/admin-source
npm install
npm run serve
```

开发服务器默认跑在 `http://localhost:8888`，`/api` 会代理到 `http://localhost:8080/admin`（见 `.env.development`）。

## 打包部署

```bash
npm run build
```

构建结果在 `dist/`，把它里面的文件复制到 Nginx 的 `html/sky/` 目录即可（对应仓库里的 `frontend/admin/`）。

生产环境接口地址在 `.env.production` 里，默认 `VUE_APP_BASE_API = /api`，由 Nginx 把 `/api/` 反向代理到后端的 `/admin/`。

## 目录说明

```
src/
├── api/            接口封装（employee、category、dish、setmeal、order、statistics…）
├── assets/         图片等静态资源
├── components/     通用组件（面包屑、汉堡按钮、图片上传、空状态…）
├── layout/         整体布局（侧边栏、导航栏、标签页）
├── router.ts       路由与权限
├── store/          Vuex 状态
├── styles/         全局样式与 Element UI 主题变量
├── utils/          axios 封装、cookie 等工具
└── views/          页面：登录、工作台、员工、分类、菜品、套餐、订单、统计
```

## 说明

- 本目录来自开源项目 [project-sky-admin-vue-ts](https://github.com/HeFeng-Lab/project-sky-admin-vue-ts)（MIT License，见 `LICENSE`），是黑马程序员《苍穹外卖》管理端的配套源码。
- 仓库里预构建的 `frontend/admin/` 与该源码同源，个别文件可能存在注释或版本差异，不影响使用；以重新构建的结果为准。