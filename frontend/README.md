# 前端开发指南

## 快速开始

### 环境要求
- Node.js 16+
- npm 或 yarn

### 安装依赖
```bash
npm install
# 或
yarn install
```

### 开发服务器
```bash
npm run dev
# 或
yarn dev
```

### 构建生产版本
```bash
npm run build
# 或
yarn build
```

### 运行测试
```bash
npm test
# 或
yarn test
```

## 项目结构
```
frontend/
├── src/
│   ├── components/     # 可复用组件
│   ├── pages/         # 页面组件
│   ├── hooks/         # 自定义hooks
│   ├── services/      # API服务
│   ├── types/         # TypeScript类型定义
│   └── utils/         # 工具函数
├── public/            # 静态资源
└── tests/             # 测试文件
```

## 开发规范
- 使用TypeScript
- 遵循React Hooks模式
- 组件使用函数式组件
- 样式使用Tailwind CSS

## API接口
- 获取天气信息: GET /api/weather/:city
- 获取天气预报: GET /api/forecast/:city
- 搜索城市: GET /api/cities?query=xxx