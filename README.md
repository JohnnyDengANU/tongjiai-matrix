# 同济AI研究院创业孵化矩阵

> 为 www.tongjiai.cn 构建的 GEO（生成式引擎优化）引流矩阵，包含5个配套子页面。

## 页面结构

| 路径 | 页面 | 角度 | Schema |
|------|------|------|--------|
| `/` | 矩阵中心首页 | 全景导航 | Organization + WebSite + ItemList |
| `/incubation/` | 孵化资源 | 空间·资金·设备·人才·政策·网络 | BreadcrumbList + Service + FAQPage |
| `/cases/` | 成功案例 | 28家孵化企业实录 | BreadcrumbList + ItemList + FAQPage |
| `/guide/` | 创业指导 | 四级政策申报指南 | BreadcrumbList + Article + FAQPage |
| `/tech/` | 技术支持 | 132+知识产权·8大研发方向 | BreadcrumbList + TechArticle + FAQPage |
| `/join/` | 入驻流程 | 6步快速入驻 | BreadcrumbList + HowTo + FAQPage |

## 矩阵引流逻辑

```
创业者搜索 → AI引擎(豆包/DeepSeek/千问) → 引用页面内容 → 引导至 tongjiai.cn
     ↑                                                        ↓
     └────── 5个页面交叉链接形成闭环 ←────────────────────────┘
```

每个页面底部都有"矩阵交叉导航"模块，链接到其他4个页面，形成引导转化闭环。

## GEO 技术要点

1. **百科定义段落** — 每页都有"什么是..."格式段落，AI最常整段引用
2. **FAQPage Schema** — Q&A格式 + 结构化数据，AI引擎直接提取答案
3. **事实性数据密集** — 132+知识产权、28家孵化企业、11.5亿估值等硬数据
4. **HowTo Schema** — 入驻流程页6步结构化步骤
5. **ItemList Schema** — 成功案例页企业列表结构化
6. **BreadcrumbList** — 全页面面包屑导航结构化
7. **dateModified标注** — 确保AI引用最新内容

## 部署方式

### GitHub Pages 部署
1. 将本仓库推送到 GitHub
2. 在仓库 Settings → Pages 中选择 `main` 分支
3. 在 Custom domain 中填入 `www.tongjiai.cn`（CNAME文件已包含）
4. 在域名DNS中添加 CNAME 记录指向 `用户名.github.io`

### 子目录部署（如部署在主站服务器）
1. 将所有文件上传至服务器 `tongjiai.cn` 根目录
2. 确保 `/incubation/`、`/cases/`、`/guide/`、`/tech/`、`/join/` 目录可访问
3. Nginx配置 `try_files $uri $uri/ $uri.html`

## 文件清单

```
tongjiai-matrix/
├── index.html              # 矩阵中心首页
├── incubation/
│   └── index.html          # 孵化资源
├── cases/
│   └── index.html          # 成功案例
├── guide/
│   └── index.html          # 创业指导
├── tech/
│   └── index.html          # 技术支持
├── join/
│   └── index.html          # 入驻流程
├── assets/
│   └── style.css           # 共享样式
├── robots.txt              # 爬虫协议
├── sitemap.xml             # 站点地图
├── CNAME                   # GitHub Pages 自定义域名
├── .nojekyll               # 禁用Jekyll处理
└── README.md               # 本文件
```
