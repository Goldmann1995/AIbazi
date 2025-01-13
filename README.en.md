# BaZi Pro - Professional Chinese Astrology System

English | [简体中文](./README.md)

A professional Chinese astrology analysis platform built on modern technology stack, dedicated to perfectly combining traditional Eastern metaphysics with modern technology.

## 🌟 Project Highlights

- 💫 Professional BaZi Algorithm Engine
- 🎯 Precise Metaphysical Analysis System
- 🌐 Multi-language Support (Chinese, English, Japanese)
- 🔒 Enterprise-grade Security
- 📱 Cross-platform Compatibility (Web, iOS, Android)
- 🎨 Customizable Themes
- 🤖 AI-Assisted Analysis

## 🔥 Business Features

- SaaS Service Model
- B2B API Support
- White-label Solutions
- Customizable Enterprise Version
- Online Payment Integration
- Subscription System

## 🛠 Technical Architecture

- **Frontend**: Next.js 14, Chakra UI, TypeScript
- **Backend**: Node.js, NestJS
- **Database**: Supabase
- **AI**: Qwen
- **Deployment**: nginx
- **Monitoring**: pm2

## Tech Stack

- Next.js 14 (App Router)
- Chakra UI
- TypeScript
- Node.js

## Features

- BaZi Chart Analysis
- Monthly Fortune Prediction
- User Authentication System
- Responsive Design
- Dark Mode Support

## Local Development

1. Clone the project
```bash
git clone [your-repository-url]
cd [project-name]
```

2. Install dependencies
```bash
npm install
# or
pnpm install
```

3. Start development server
```bash
npm run dev
# or
pnpm dev
```

Visit [http://localhost:3000](http://localhost:3000) to view the application.

## Server Deployment

### 1. Environment Setup

```bash
# Install Node.js
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18

# Install PM2
npm install -g pm2
```

### 2. Project Configuration

Create `ecosystem.config.js`:
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

### 3. Nginx Configuration

```nginx
server {
    listen 80;
    server_name example.com;

    access_log /var/log/nginx/example.com.access.log;
    error_log /var/log/nginx/example.com.error.log;

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

## 🌍 Business Cooperation

### Investment Highlights
- Market Size: Global metaphysics market exceeds $100 billion
- Growth Potential: Annual growth rate over 15%
- Technical Barrier: Patented algorithm engine
- Business Model: Subscription + API + Enterprise Solutions
- Globalization: Multi-language and region support

### Business Model
- Basic Version: Free to use
- Professional Version: Monthly/Annual subscription
- Enterprise Version: Customized solutions
- API Services: Pay-per-call
- Consulting Services: Expert online consultation

## 🤝 Community & Support

- [Official Website](https://example.com)
- [Live Demo](https://demo.example.com)
- [Documentation](https://docs.example.com)
- [API Documentation](https://api.example.com)
- [Community Forum](https://forum.example.com)

## 📈 Roadmap

- [x] Core Algorithm Engine
- [x] Basic Chart Analysis
- [ ] AI-Powered Analysis
- [ ] Multi-language Support
- [ ] Mobile Applications
- [ ] Enterprise Version
- [ ] Global Deployment

## 🌟 Our Vision

Dedicated to spreading traditional Eastern metaphysical culture globally through modern technology, building the most professional metaphysical analysis platform.

## 📞 Business Contact

- Email: business@example.com
- WeChat: BaziPro
- Twitter: @BaziPro
- LinkedIn: BaziPro Official

## 📜 License

This project is licensed under the GNU Affero General Public License v3.0.
See the [LICENSE](LICENSE) file for details.

---

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Goldmann1995/AIbazi&type=Date)](https://star-history.com/#Goldmann1995/AIbazi&Date)

If you like this project, please give us a Star ⭐!
