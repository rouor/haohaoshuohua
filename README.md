
# 好好说话 · HaoHaoShuoHua

把容易引发冲突的表达，转化为更容易被对方接受的方式。
也可以是直男翻译器，把伤人的话用非暴力沟通的方式说一遍

## 为什么做这个
很多关系的裂痕，不是因为我们不爱对方，而是因为我们不知道怎么说。
同样一件事，说法不同，结果天壤之别。
我最初动力是我身边人，有好几个人都不能好好说话。
"你怎么又忘了！" 和 "这件事对我很重要，我们能不能一起想个办法记住它？" ——传递的是同一个需求，但一个关上了门，一个打开了门。
好好说话是一个 AI 沟通转化工具。你把想说的话输进来，哪怕措辞很冲、情绪很满，它帮你把同一个意思，用不伤人、又真实的方式重新说一遍。

部署在vercel，国内可能不容易点击，国内部署还在更新，敬请期待

## 它能做什么
输入你想说的原话，选择沟通场景和表达风格，它会同时生成三个版本：
版本作用🕊️ 降冲突版本去掉攻击性，用中性语言表达同一件事🌱 建设性版本加入共情，表达真实需求，给出可执行的建议🎨 风格强化版本按你选的风格深度定制
还会附上一句"对方可能的感受"——让你在说出口之前，先看见对方的处境。
三种沟通场景

### 💑 伴侣：亲密关系里的摩擦与误解
### 👨‍👩‍👧 亲子：教养压力下的管教与对话
### 💼 职场：反馈、边界、协作中的表达难题

## 四种表达风格

🌸 温和共情型 — 让对方感到被理解
🔷 理性清晰型 — 简洁直接，不带情绪攻击
🛡️ 坚定边界型 — 立场清晰，不讨好，不回避
✨ 鼓励引导型 — 正向反馈，用引导代替命令


## 背后的沟通原则
好好说话不是让你说"好听的话"，而是帮你说"真实又不伤人的话"。它遵循几条基本原则：

描述具体行为，而不是贴标签（"你没洗碗" 而非 "你从来不做家务"）
用**"我感受…"** 表达自己，而不是用 "你总是…" 指责对方
表达真实需求，而不是发泄情绪
给出可执行的请求，而不是模糊的抱怨
让对方感觉被理解，而不是被纠正


## 技术架构
浏览器 (index.html)
    │
    │  POST /api/chat
    ▼
Vercel Serverless Function (api/chat.js)
    │
    │  x-api-key: ANTHROPIC_API_KEY
    ▼
Anthropic API (claude-sonnet-4-6)
前端为纯原生 HTML/CSS/JS，无框架依赖。后端为单个 Vercel Serverless Function，仅做 API 代理，API Key 存储在服务端环境变量中，不暴露给浏览器。

## 部署方法
方式一：GitHub + Vercel（推荐）
① Fork 或克隆本仓库
bashgit clone https://github.com/你的用户名/haohaoshuohua.git
cd haohaoshuohua
② 导入到 Vercel
打开 vercel.com → Add New Project → 选择本仓库 → Deploy
③ 配置 API Key
Vercel 项目页 → Settings → Environment Variables → 添加：
ANTHROPIC_API_KEY = sk-ant-xxxxxxxxxxxxxxxx
保存后，回到 Deployments → 最新部署 → Redeploy
④ 完成
访问 Vercel 分配的域名即可使用，也可在 Settings 中绑定自定义域名。
后续更新代码只需 git push，Vercel 会自动重新部署。

## 方式二：直接拖拽到 Vercel（无需 GitHub）

下载本项目文件夹
打开 vercel.com → Add New Project → 拖入文件夹
同上配置 ANTHROPIC_API_KEY 环境变量 → Redeploy


文件结构
haohaoshuohua/
├── index.html        # 前端页面（全部 UI 逻辑）
├── vercel.json       # Vercel 路由配置
├── api/
│   └── chat.js       # API 代理（保护 API Key）
└── README.md         # 本文件

## 关于
好好说话由 一淼AI创新工作室 独立开发，是 AI 人文教育产品系列的一部分。
核心信念：用AI让我们升级为“更高版本的人类操作系统”
我作为设计师的第一个vibecoding 作品，好开心，很想别人给我反馈：）
