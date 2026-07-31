# Kindle 信息看板

纯静态、可部署 GitHub Pages 的 Kindle 信息看板。一个 HTML 文件包含全部功能，无依赖、无构建。

## 功能

| 模块 | 说明 | 数据源 |
|------|------|--------|
| ⏱ 当前时间 | 实时数字时钟，日期 + 星期 | 浏览器本地 |
| 🌤 天气预报 | 温度、湿度、风速、天气描述 | [Open-Meteo](https://open-meteo.com/)（免费，无需 API Key） |
| 📖 每日一句 | 中英文名言，API 失败时自动降级到内置名言库 | [Quotable](https://github.com/lukePeavey/quotable) |
| 🖼 海报 | 自定义图片 URL 展示 | 用户配置 |
| ⚙ 设置 | 经纬度、城市、温度单位、海报 URL、刷新间隔 | 保存至 localStorage |

## 快速开始

### 本地使用

直接用浏览器打开 `index.html`：

```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

或用任意静态服务器：

```bash
python3 -m http.server 8080
# 浏览器访问 http://localhost:8080
```

### 部署到 GitHub Pages

1. Fork 或上传本目录到你的 GitHub 仓库
2. 进入仓库 **Settings → Pages**
3. **Source** 选择 `main` 分支，目录选 `/ (root)`（或把文件放在 `docs/` 下选 `/docs`）
4. 保存，等待 1-2 分钟后访问 `https://<你的用户名>.github.io/<仓库名>/`

## 项目结构

```
kindle-dashboard/
├── index.html      # 主页面（包含所有 CSS + JS）
├── README.md       # 本文件
└── USER_GUIDE.md   # 用户指南
```

## 技术要点

- **零依赖**：纯 HTML/CSS/JS，无 npm、无构建、无框架
- **响应式**：适配桌面、平板、Kindle 浏览器
- **暗色模式**：跟随系统 `prefers-color-scheme`
- **离线友好**：天气/名言失败时有降级策略，时钟不受影响
- **隐私优先**：所有设置存储在浏览器 localStorage，不上传任何数据

## 天气 API

使用 [Open-Meteo](https://open-meteo.com/) 免费天气 API：
- 无需注册、无需 API Key
- 数据来源：全球气象模型（GFS/ECMWF）
- 免费商用，速率限制 10,000 次/天

## License

MIT
