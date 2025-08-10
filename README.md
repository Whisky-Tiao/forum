# 大学腾飞营论坛 (University Forum)

一个功能完整的大学学员内部论坛系统，支持多语言、用户认证、帖子管理、评论系统、收藏功能等。

## 功能特性

### 1. 多语言支持
- 支持中文和英文界面
- 用户可以根据需要切换语言
- 确保广泛的用户群体都能顺利使用

### 2. 用户认证系统
- 用户注册和登录功能
- 用户角色管理（普通用户和管理员）
- 密码复杂度要求：
  - 至少8个字符
  - 包含大写字母、小写字母、数字和特殊字符
- 管理员可以删除和编辑所有帖子，普通用户只能操作自己的帖子

### 3. 帖子管理
- 用户可以发布帖子，支持标题、内容、标签
- 支持编辑和删除自己发布的帖子
- 管理员有权限管理所有帖子
- 支持分页，减少页面加载的压力

### 4. 评论系统
- 用户可以对帖子进行评论
- 每个帖子可以有多个评论
- 支持评论删除，只有评论的作者或管理员可以删除评论

### 5. 收藏功能
- 用户可以收藏帖子
- 收藏功能会保存帖子，方便用户快速访问
- AJAX请求用于无刷新操作，提升用户体验

### 6. 响应式设计
- 使用Bootstrap框架实现了良好的响应式设计
- 确保在桌面和移动端都能良好展示

### 7. 安全性
- 集成了CSRF保护，防止跨站请求伪造攻击
- 密码采用哈希加密存储，确保用户数据安全

### 8. AJAX交互
- 使用AJAX实现无刷新操作
- 包括帖子收藏和帖子删除等功能
- 提升用户体验

### 9. 后台通知
- 管理员可以给用户发送通知
- 用于提醒重要信息或更新

### 10. 数据库
- 使用 SQLite 数据库
- 简化了部署，并能处理较大规模的数据

### 11. 简洁的UI设计
- 现代化的UI设计
- 色调清新，符合现代网页设计趋势
- 注重用户体验

## 安装和运行

### 环境要求
- Python 3.7+
- pip

### 安装步骤

1. 克隆或下载项目到本地
2. 进入项目目录
3. 安装依赖包：
   ```bash
   pip install -r requirements.txt
   ```

4. 运行应用：
   ```bash
   python app.py
   ```

5. 在浏览器中访问：`http://localhost:5000`

### 初始设置

首次运行时，系统会自动创建数据库和必要的表结构。

### 创建管理员账户

在数据库中手动设置用户角色为 'admin'：

```sql
UPDATE users SET role = 'admin' WHERE username = 'your_username';
```

## 项目结构

```
university_forum/
├── app.py                 # 主应用文件
├── requirements.txt       # 项目依赖
├── forum.db              # SQLite数据库文件（自动生成）
├── templates/            # HTML模板文件
│   ├── base.html         # 基础模板
│   ├── index.html        # 首页模板
│   ├── login.html        # 登录页面
│   ├── register.html     # 注册页面
│   ├── new_post.html     # 发布帖子页面
│   ├── view_post.html    # 帖子详情页面
│   ├── edit_post.html    # 编辑帖子页面
│   ├── favorites.html    # 收藏页面
│   ├── notifications.html # 通知页面
│   └── admin_notifications.html # 管理员通知页面
├── static/               # 静态文件目录
└── uploads/              # 上传文件目录（自动创建）
```

## 主要路由

- `/` - 首页，显示帖子列表
- `/register` - 用户注册
- `/login` - 用户登录
- `/logout` - 用户登出
- `/post/new` - 发布新帖子
- `/post/<id>` - 查看帖子详情
- `/post/<id>/edit` - 编辑帖子
- `/favorites` - 查看收藏的帖子
- `/notifications` - 查看通知
- `/admin/notifications` - 管理员发送通知
- `/language/<lang>` - 切换语言

## 技术栈

- **后端框架**: Flask
- **用户认证**: Flask-Login
- **表单处理**: Flask-WTF
- **国际化**: Flask-Babel
- **数据库**: SQLite
- **前端框架**: Bootstrap 5
- **JavaScript库**: jQuery
- **图标库**: Font Awesome

## 安全特性

- 密码哈希加密存储
- CSRF保护
- 用户权限验证
- 输入验证和清理
- SQL注入防护

## 贡献

欢迎提交Issue和Pull Request来改进这个项目。

## 许可证

MIT License 