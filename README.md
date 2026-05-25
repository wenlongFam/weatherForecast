# 🌤️ 天气预报

一个精美的移动端天气预报应用，数据来自中国天气网（weather.com.cn），支持自动定位、逐时预报、7日预报、生活指数等功能。

## ✨ 功能特性

- 📍 **自动定位** — 打开页面自动获取位置，定位到当前城市
- 🌡️ **实时天气** — 当前温度、天气状况、湿度、风力、降水量
- 🕐 **逐时预报** — 24小时温度变化，横向滑动查看
- 📅 **7日预报** — 未来7天天气预报，温度区间可视化
- 👕 **生活指数** — 穿衣/运动/洗车/紫外线指数，点击查看详情
- 🌅 **日出日落** — 当天日出日落时间
- 🎨 **动态天气动画** — 根据天气类型展示晴天/雨天/雪天/雾天等动画场景
- 🔍 **城市搜索** — 支持搜索全国各城市天气
- 📱 **移动端优化** — 适配各种手机屏幕，支持 PWA 添加到主屏幕

## 🛠️ 技术栈

- **框架**: [Next.js 14](https://nextjs.org/) (App Router)
- **语言**: TypeScript
- **样式**: Tailwind CSS 4 + shadcn/ui
- **动画**: Framer Motion
- **数据来源**: 中国天气网 (weather.com.cn)
- **定位**: Browser Geolocation API + Nominatim (OpenStreetMap)

## 📁 项目结构

```
src/
├── app/
│   ├── page.tsx                  # 主页面（天气展示）
│   ├── layout.tsx                # 全局布局
│   ├── globals.css               # 全局样式 + 动画
│   └── api/
│       ├── weather/
│       │   └── route.ts          # 天气数据 API（抓取天气网）
│       ├── weather/
│       │   ├── search/route.ts   # 城市搜索 API
│       │   └── geolocation/route.ts  # 逆地理解码 API
│       └── route.ts              # 健康检查
├── components/ui/                # shadcn/ui 组件库
├── hooks/                        # 自定义 Hooks
└── lib/
    └── weather-utils.ts          # 天气数据解析工具
public/
├── manifest.json                 # PWA manifest
└── weather/                      # 天气主题图片
```

## 🚀 快速开始

### 1. 克隆项目

```bash
git clone https://github.com/your-username/weather-app.git
cd weather-app
```

### 2. 安装依赖

```bash
npm install
# 或
bun install
```

### 3. 配置环境变量

```bash
cp .env.example .env
```

### 4. 启动开发服务器

```bash
npm run dev
```

打开 [http://localhost:3000](http://localhost:3000) 查看效果。

### 5. 构建生产版本

```bash
npm run build
npm start
```

## 📱 移动端适配

- 使用 `max-w-[480px]` 适配手机屏幕
- 禁止页面缩放，优化触摸交互
- 支持 iPhone 刘海屏/灵动岛安全区域
- 支持 PWA，可添加到手机主屏幕
- 自定义横向滚动条样式

## 🌐 API 说明

| 接口 | 参数 | 说明 |
|------|------|------|
| `GET /api/weather?city=<code>` | city: 9位城市代码 | 获取天气数据 |
| `GET /api/weather/search?q=<name>` | q: 城市名 | 搜索城市 |
| `GET /api/weather/geolocation?lat=<lat>&lng=<lng>` | lat/lng: 经纬度 | 逆地理解码 |

## 📄 License

MIT
