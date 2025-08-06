# Cloud Demo - Vue.js 项目

这是一个基于Vue.js的前端项目，包含登录页面和商品管理功能。

## 功能特性

### 登录页面 (`/login`)
- **密码登录**: 使用用户名和密码进行登录
- **LDAP登录**: 使用LDAP服务器进行身份验证
- **GitHub登录**: 通过GitHub OAuth进行第三方登录

### 商品管理页面 (`/products`)
- **商品列表**: 显示所有商品的ID和名称
- **添加商品**: 通过模态框添加新商品
- **编辑商品**: 修改现有商品信息
- **删除商品**: 删除商品（带确认对话框）

## 技术栈

- Vue 3
- Vue Router 4
- Axios (HTTP客户端)
- 现代CSS (Grid, Flexbox)

## 安装和运行

### 前提条件
确保你的系统已安装：
- Node.js (版本 14 或更高)
- npm 或 yarn

### 安装依赖
```bash
npm install
```

### 开发模式运行
```bash
npm run serve
```

### 构建生产版本
```bash
npm run build
```

### 前提条件
1. 确保后端服务运行在 `localhost:8000`
2. 后端API接口已实现并可用
3. 支持CORS跨域请求

## 项目结构

```
src/
├── api/           # API服务
│   └── index.js   # API配置和接口定义
├── router/        # 路由配置
│   └── index.js   # 路由定义和守卫
├── views/         # 页面组件
│   ├── LoginDemo.vue      # 登录页面
│   └── ProductList.vue # 商品列表页面
├── components/    # 通用组件
├── assets/        # 静态资源
├── App.vue        # 根组件
└── main.js        # 应用入口
```

## API接口

### 登录相关
- `POST http://localhost:8000/api/auth/password` - 密码登录
- `POST http://localhost:8000/api/auth/ldap` - LDAP登录
- `GET http://localhost:8000/api/auth/github` - 获取GitHub授权URL
- `POST http://localhost:8000/api/auth/github/callback` - GitHub回调处理

### 商品相关
- `GET http://localhost:8000/api/products` - 获取商品列表
- `POST http://localhost:8000/api/products` - 创建商品
- `PUT http://localhost:8000/api/products/:id` - 更新商品
- `DELETE http://localhost:8000/api/products/:id` - 删除商品

## 环境配置

项目已配置为使用真实的后端API：

- **后端地址**: `http://localhost:8000/api`
- **登录接口**: 支持密码登录、LDAP登录、GitHub登录
- **商品管理**: 完整的CRUD操作

确保后端服务运行在 `localhost:8000` 端口。

## 路由守卫

项目实现了路由守卫功能：
- 未登录用户访问需要认证的页面会被重定向到登录页面
- 登录成功后会自动跳转到商品列表页面

## 样式特点

- 响应式设计，适配不同屏幕尺寸
- 现代化的UI设计，包含渐变背景和阴影效果
- 蓝色主题色调，符合用户偏好
- 良好的用户体验，包含加载状态和错误提示

## 技术亮点

- ✅ Vue 3 Composition API
- ✅ Vue Router 4 路由管理
- ✅ 现代化CSS设计
- ✅ 组件化架构
- ✅ 真实API接口集成
- ✅ 错误处理机制
- ✅ 用户体验优化
