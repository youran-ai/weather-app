# 后端开发指南

## 快速开始

### 环境要求
- Node.js 16+
- MongoDB 5.0+
- OpenWeatherMap API密钥

### 安装依赖
```bash
npm install
```

### 环境配置
复制 `.env.example` 为 `.env` 并配置：
```
PORT=3000
MONGODB_URI=mongodb://localhost:27017/weather-app
OPENWEATHER_API_KEY=your_api_key_here
JWT_SECRET=your_jwt_secret
```

### 开发服务器
```bash
npm run dev
```

### 构建和运行
```bash
npm run build
npm start
```

## API端点设计

### 天气相关
- `GET /api/weather/current/:city` - 获取当前天气
- `GET /api/weather/forecast/:city` - 获取5天预报
- `GET /api/weather/history/:city` - 获取历史天气

### 用户相关
- `POST /api/auth/register` - 用户注册
- `POST /api/auth/login` - 用户登录
- `GET /api/user/favorites` - 获取收藏城市
- `POST /api/user/favorites` - 添加收藏城市

## 项目结构
```
backend/
├── src/
│   ├── routes/        # 路由定义
│   ├── models/        # 数据模型
│   ├── services/      # 业务逻辑
│   ├── utils/         # 工具函数
│   └── middleware/    # 中间件
├── tests/             # 测试文件
└── dist/              # 编译输出
```

## 开发规范
- 使用TypeScript
- RESTful API设计
- 统一的错误处理
- 输入验证和清理
- 使用JWT进行身份验证