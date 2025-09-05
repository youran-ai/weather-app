# 天气查询应用 - 四人协作项目

## 项目简介
这是一个基于天气API的实时天气查询应用，用户可以通过城市名称查询当前天气信息、未来预报以及历史天气数据。项目采用前后端分离架构，包含数据可视化功能。

## 技术栈
- **前端**: React.js + TypeScript + Tailwind CSS
- **后端**: Node.js + Express.js + TypeScript
- **数据处理**: Python + Pandas + Matplotlib
- **数据库**: MongoDB
- **API**: OpenWeatherMap API

## 团队成员分工

### LYL: 前端开发 (Frontend Developer)
**负责目录**: `frontend/`
**主要职责**:
- 设计并实现用户界面
- 实现天气查询表单和结果展示
- 集成天气图标和动画效果
- 响应式设计适配移动端
- 编写前端单元测试

**技术要点**:
- React Hooks状态管理
- Axios API调用
- CSS Grid/Flexbox布局
- Jest测试框架

### LSJ: 后端开发 (Backend Developer)
**负责目录**: `backend/`
**主要职责**:
- 设计和实现RESTful API
- 集成第三方天气API
- 实现用户认证和授权
- 数据库设计和操作
- 编写API文档和测试

**技术要点**:
- Express.js路由设计
- MongoDB数据建模
- JWT身份验证
- Swagger API文档

### LYX: 数据处理 (Data Processing)
**负责目录**: `data-processing/`
**主要职责**:
- 天气数据清洗和预处理
- 历史天气数据分析
- 生成天气趋势图表
- 数据可视化脚本开发
- 数据质量监控

**技术要点**:
- Python数据处理
- Pandas数据分析
- Matplotlib/Seaborn可视化
- 数据导出格式优化

### LTY: 文档和测试 (Documentation & Testing)
**负责目录**: `documentation/`
**主要职责**:
- 编写项目文档和用户指南
- 设计测试用例和测试计划
- 执行集成测试和性能测试
- 部署文档和运维指南
- 项目演示和汇报材料

**技术要点**:
- Markdown文档编写
- Postman测试脚本
- 性能测试工具
- CI/CD流程配置

## Git协作工作流

### 分支策略 (Git Flow)
```
main (主分支)
├── develop (开发分支)
│   ├── feature/frontend-ui
│   ├── feature/backend-api
│   ├── feature/data-analysis
│   └── feature/documentation
├── release/v1.0.0
└── hotfix/critical-bug
```

### 工作流程
1. **每日同步**: 每天开始工作前从develop分支拉取最新代码
2. **功能开发**: 从develop创建功能分支进行开发
3. **代码审查**: 通过Pull Request进行代码审查
4. **合并策略**: 功能完成后合并回develop分支
5. **发布流程**: develop测试稳定后合并到main分支

### 提交规范
- **格式**: `type(scope): description`
- **类型**: feat, fix, docs, style, refactor, test, chore
- **示例**: `feat(frontend): add weather search form`

### 协作规则
- **每日站会**: 每天15分钟同步进度
- **代码审查**: 至少一人审查后才能合并
- **冲突解决**: 优先沟通，避免强制推送
- **文档更新**: 每次功能变更同步更新文档

## 项目里程碑

### 第1周: 项目初始化
- [ ] 环境搭建和依赖安装
- [ ] 基础项目结构创建
- [ ] API接口设计文档

### 第2周: 核心功能开发
- [ ] 前端基础界面完成
- [ ] 后端API接口实现
- [ ] 基础数据处理脚本

### 第3周: 功能完善
- [ ] 高级功能开发
- [ ] 数据可视化实现
- [ ] 测试用例编写

### 第4周: 测试和部署
- [ ] 全面测试和bug修复
- [ ] 项目文档完善
- [ ] 最终演示准备

## 快速开始

### 环境要求
- Node.js 16+
- Python 3.8+
- MongoDB 5.0+
- Git

### 安装步骤
1. 克隆项目: `git clone [repository-url]`
2. 安装依赖: 各目录下执行相应安装命令
3. 配置环境: 复制`.env.example`为`.env`并配置
4. 启动服务: 按照各模块README启动服务

## 联系信息
- 项目负责人: [姓名]
- 技术顾问: [姓名]
- 项目仓库: [GitHub URL]

---
*本项目为教学实践项目，遵循MIT开源协议*