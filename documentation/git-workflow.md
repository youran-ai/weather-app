# Git协作工作流程指南

## 团队分支管理策略

### 1. 分支结构说明
```
main (生产分支)
├── develop (开发主分支)
│   ├── feature/frontend-ui (前端界面)
│   ├── feature/backend-api (后端接口)
│   ├── feature/data-analysis (数据处理)
│   └── feature/documentation (文档测试)
├── release/v1.0.0 (发布分支)
├── hotfix/critical-bug (紧急修复)
└── personal/[成员名]/[功能名] (个人开发分支)
```

### 2. 每日工作流程

#### 早晨同步 (9:00 AM)
```bash
# 切换到develop分支
git checkout develop

# 拉取最新代码
git pull origin develop

# 更新个人功能分支
git checkout feature/frontend-ui
git rebase develop
```

#### 工作开始前
```bash
# 检查当前分支状态
git status

# 查看最近的提交历史
git log --oneline -5

# 确认没有未提交的更改
git diff --cached
```

### 3. 功能开发流程

#### 创建功能分支
```bash
# 从develop创建新的功能分支
git checkout develop
git pull origin develop
git checkout -b feature/weather-search-form

# 或者基于个人分支创建
git checkout -b personal/[你的名字]/weather-search-form
```

#### 日常开发提交
```bash
# 查看更改的文件
git status

# 添加文件到暂存区
git add .
# 或者添加特定文件
git add frontend/src/components/WeatherForm.tsx

# 提交更改（遵循提交规范）
git commit -m "feat(frontend): add weather search form component"

# 推送到远程仓库
git push origin feature/weather-search-form
```

#### 提交消息规范
**格式**: `type(scope): description`

**类型说明**:
- `feat`: 新功能
- `fix`: 修复bug
- `docs`: 文档更新
- `style`: 代码格式调整
- `refactor`: 代码重构
- `test`: 测试相关
- `chore`: 构建过程或辅助工具的变动

**示例**:
```
feat(frontend): add responsive weather card component
fix(backend): resolve API timeout issue
docs(readme): update installation instructions
style(frontend): format code with prettier
```

### 4. 代码审查流程

#### 创建Pull Request
1. 在GitHub/GitLab上创建PR
2. 填写PR模板
3. 指定至少一名审查者
4. 添加相关标签

#### PR模板示例
```markdown
## 变更说明
简要描述这次更改的内容

## 测试步骤
1. 如何测试这个功能
2. 预期结果是什么

## 相关Issue
关联的issue编号: #123

## 截图/录屏
(如有UI变更请添加截图)
```

#### 审查检查清单
- [ ] 代码符合项目规范
- [ ] 功能测试通过
- [ ] 文档已更新
- [ ] 没有引入新bug
- [ ] 性能影响评估

### 5. 冲突解决指南

#### 预防冲突
```bash
# 经常同步develop分支
git checkout develop
git pull origin develop
git checkout feature/your-feature
git rebase develop
```

#### 解决冲突步骤
1. **识别冲突文件**
```bash
git status
```

2. **手动解决冲突**
打开冲突文件，找到标记的冲突区域:
```
<<<<<<< HEAD
当前分支的代码
=======
合并分支的代码
>>>>>>> feature/other-feature
```

3. **标记为已解决**
```bash
git add [冲突文件]
git commit -m "resolve merge conflict in [文件名]"
```

### 6. 紧急情况处理

#### 紧急修复 (hotfix)
```bash
# 从main创建hotfix分支
git checkout main
git pull origin main
git checkout -b hotfix/critical-bug-fix

# 修复后合并回main和develop
git checkout main
git merge hotfix/critical-bug-fix
git checkout develop
git merge hotfix/critical-bug-fix
```

#### 回滚操作
```bash
# 查看提交历史
git log --oneline

# 回滚到特定提交
git reset --hard [commit-hash]

# 撤销特定提交的更改
git revert [commit-hash]
```

### 7. 团队协作规范

#### 每日同步会议 (15分钟)
- 昨天完成了什么
- 今天计划做什么
- 遇到了什么阻碍

#### 代码审查轮值表
| 星期 | 审查者 |
|------|--------|
| 周一 | 成员A |
| 周二 | 成员B |
| 周三 | 成员C |
| 周四 | 成员D |
| 周五 | 集体审查 |

#### 沟通渠道
- **即时沟通**: 微信群/Slack
- **技术讨论**: GitHub Issues
- **文档共享**: 腾讯文档/Notion
- **会议记录**: 会议纪要文档

### 8. 常用命令速查表

#### 基础命令
```bash
git init                    # 初始化仓库
git clone [url]            # 克隆仓库
git status                 # 查看状态
git add [file]            # 添加文件
git commit -m "message"   # 提交更改
git push origin [branch]  # 推送分支
git pull origin [branch]  # 拉取更新
```

#### 分支操作
```bash
git branch                 # 列出分支
git branch [name]         # 创建分支
git checkout [name]       # 切换分支
git merge [branch]        # 合并分支
git branch -d [name]      # 删除分支
```

#### 查看历史
```bash
git log                   # 查看提交历史
git log --oneline        # 简洁历史
git diff [file]          # 查看差异
git show [commit]        # 查看提交详情
```

### 9. 最佳实践建议

1. **小步快跑**: 频繁提交小的更改
2. **及时同步**: 每天至少同步一次develop分支
3. **清晰命名**: 分支和提交消息要清晰明了
4. **测试先行**: 每次提交前运行测试
5. **文档同步**: 代码变更时同步更新文档

### 10. 故障排除

#### 常见问题解决
- **忘记拉取最新代码**: `git pull --rebase origin develop`
- **提交信息写错**: `git commit --amend -m "新消息"`
- **误提交文件**: `git reset HEAD [文件名]`
- **需要强制推送**: `git push --force-with-lease origin [分支名]`

#### 寻求帮助
1. 先查看本指南
2. 搜索相关Issue
3. 询问团队成员
4. 联系项目管理员

---
*最后更新: 2024年*