# BaZi Pro - 专业八字命理系统 | Professional Chinese Astrology System

[English](./README.en.md) | 简体中文

基于现代技术栈打造的专业级八字命理分析平台，致力于将传统东方命理文化与现代技术完美结合。

## 🌟 项目亮点

- 💫 专业级八字算法引擎
- 🎯 精准的命理分析系统
- 🌐 支持多语言（中文、英文、日文）
- 🔒 企业级安全保障
- 📱 全平台适配（Web、iOS、Android）
- 🎨 可自定义主题
- 🤖 AI 辅助解盘

## 🔥 商业特色

- 提供 SaaS 服务模式
- B2B API 接口支持
- 白标解决方案
- 可定制企业版
- 在线支付集成
- 会员订阅系统

## 🛠 技术架构

- **前端**: Next.js 14, Chakra UI, TypeScript
- **后端**: Node.js, NestJS
- **数据库**: Supabase
- **AI**: Qwen
- **部署**: ngnix
- **监控**: pm2

## 技术栈

- Next.js 14 (App Router)
- Chakra UI
- TypeScript
- Node.js

## 功能特点

- 八字命理分析
- 流月运势预测
- 用户认证系统
- 响应式设计
- 深色模式支持

## 本地开发

1. 克隆项目
```bash
git clone [your-repository-url]
cd [project-name]
```

2. 安装依赖
```bash
npm install
# 或
pnpm install
```

3. 启动开发服务器
```bash
npm run dev
# 或
pnpm dev
```

访问 [http://localhost:3000](http://localhost:3000) 查看应用。

## 服务器部署

### 1. 环境准备

```bash
# 安装 Node.js
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18

# 安装 PM2
npm install -g pm2
```

### 2. 项目配置

创建 `ecosystem.config.js`:
```javascript
module.exports = {
  apps: [{
    name: "bazi-app",
    script: "npm",
    args: "start",
    env: {
      NODE_ENV: "production",
      PORT: 3000
    },
    instances: 1,
    autorestart: true,
    watch: false,
    max_memory_restart: '1G',
    error_file: 'logs/err.log',
    out_file: 'logs/out.log',
    log_date_format: 'YYYY-MM-DD HH:mm:ss'
  }]
}
```

### 3. Nginx 配置

```nginx
server {
    listen 80;
    server_name einfach.lol;

    access_log /var/log/nginx/einfach.lol.access.log;
    error_log /var/log/nginx/einfach.lol.error.log;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_cache_bypass $http_upgrade;
    }
}
```

### 4. 部署脚本

创建 `deploy.sh`:
```bash
#!/bin/bash

# 更新代码
git pull

# 安装依赖
npm install

# 构建项目
npm run build

# 重启服务
pm2 restart ecosystem.config.js
```

### 5. 备份脚本

创建 `backup.sh`:
```bash
#!/bin/bash
DATE=$(date +%Y%m%d)
BACKUP_DIR="/path/to/backups"
PROJECT_DIR="/path/to/project"

# 创建备份
tar -czf $BACKUP_DIR/bazi-app-$DATE.tar.gz $PROJECT_DIR

# 保留最近7天的备份
find $BACKUP_DIR -name "bazi-app-*.tar.gz" -mtime +7 -delete
```

### 6. 常用维护命令

```bash
# 启动服务
pm2 start ecosystem.config.js

# 查看状态
pm2 status

# 查看日志
pm2 logs bazi-app

# 重启服务
pm2 restart bazi-app

# 停止服务
pm2 stop bazi-app
```

## 环境变量配置

创建 `.env.production`:
```env
NEXT_PUBLIC_API_URL=your-api-url
# 其他环境变量
```

## 安全建议

- 使用 HTTPS（Let's Encrypt）
- 配置防火墙规则
- 定期更新依赖包
- 设置错误页面
- 配置日志轮转
- 设置监控告警

## 🌍 商业合作

### 投资亮点
- 市场规模：全球命理市场规模超过1000亿美元
- 增长潜力：年增长率达15%以上
- 技术壁垒：专利级算法引擎
- 商业模式：订阅+API+企业解决方案
- 全球化：支持多语言多地区部署

### 商业模式
- 基础版：免费使用
- 专业版：月度/年度订阅
- 企业版：定制化解决方案
- API服务：按调用次数计费
- 咨询服务：专家在线咨询

## 🤝 社区与支持

- [官方网站](https://einfach.lol)

## 📈 项目路线图

- [x] 核心算法引擎
- [x] 基础命盘分析
- [ ] AI 智能解盘
- [ ] 多语言支持
- [ ] 移动应用
- [ ] 企业版本
- [ ] 全球化部署

## 🌟 我们的愿景

致力于将东方传统命理文化通过现代技术传播到全球，打造最专业的命理分析平台。

## 📞 商务合作

- 邮箱：zhichao_jin19@126.com
- 微信：nongxingbuziran


---


## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Goldmann1995/AIbazi&type=Date)](https://star-history.com/#Goldmann1995/AIbazi&Date)

如果您喜欢这个项目，请给我们一个 Star ⭐！

## 📜 许可证

本项目采用 GNU Affero General Public License v3.0 开源许可证。
详情请参见 [LICENSE](LICENSE) 文件。