# 党媛媛 Yuanyuan Dang · 学术个人主页

模仿 [Kate Wenqi Zhu](https://katewenqizhu.github.io/)（基于 al-folio 主题）的页面结构与设计语言，为党老师定制的纯静态学术主页。**无需任何构建工具**——直接打开 `index.html` 即可预览，推送至 GitHub 仓库即可发布。

## 站点结构（与 Kate 站点逐页对应）

| 页面 | 对应 Kate 站点 | 内容 |
|------|---------------|------|
| `index.html` | About（首页） | 头像 + 简介中英文、研究兴趣卡片、教育与履历时间线、News、代表论文（含 UTD24 徽章） |
| `publications.html` | Publications | 按研究方向分组的编号式论文列表（顶刊 / eHealth / 会议 / 早期工作），含 DBLP、DOI 链接 |
| `projects.html` | Project | 在研项目卡片：国基金面上/青年、信宜数字孪生医共体、省重点实验室、科技商学院、县域经济等 |
| `teaching.html` | Teaching | 四门课程 + 研究生招生说明 |
| `awards.html` | Awards | 国家级青年人才、主持/参与基金项目、学术兼职 |

## 内容来源（事实核验说明）

所有条目均来自可核验来源，**未杜撰任何内容**：

- 论文条目：DBLP（https://dblp.org/pid/135/9677.html）、华南理工工商管理学院官网教师页、MIS Quarterly 官网（DOI: 10.25300/MISQ/2022/16201）、Emerald 官网（IT&P, DOI: 10.1108/itp-11-2021-0901）
- 履历/项目：华南理工官网教师页（助理研究员 2021–2024、副教授 2024–）、智慧树课程团队介绍、用户档案
- 《管理科学学报》论文及 Management Science 在审论文：官方介绍中提及但具体条目未公开，页面上以「待补充」明确标注，**未编造标题**

## 部署到 GitHub Pages（与 Kate 同款部署方式）

Kate 的站点是 GitHub Pages 托管的。本站为纯静态 HTML，部署更简单。

你的 GitHub 账号为 **YuanyuanDang777**，部署后站点地址为 `https://yuanyuandang777.github.io`。

### 方式一：命令行推送

1. 在 GitHub 上新建仓库，命名为 **`yuanyuandang777.github.io`**（必须是这个名字）
2. 在本目录下执行：
   ```bash
   cd dangyuanyuan-homepage
   git init
   git add .
   git commit -m "Initial release of personal academic homepage"
   git branch -M main
   git remote add origin https://github.com/YuanyuanDang777/yuanyuandang777.github.io.git
   git push -u origin main
   ```
3. 仓库 Settings → Pages → Source 选择 `main` 分支 `/ (root)`（新仓库通常默认已启用）
4. 约 1 分钟后访问 **https://yuanyuandang777.github.io** 即可看到网站

### 方式二：网页上传（无需命令行）

1. 在 GitHub 上新建仓库 `yuanyuanDang777.github.io`
2. 仓库页面 → `Add file` → `Upload files` → 拖入本目录全部文件 → `Commit changes`
3. Settings → Pages 确认 Source 为 `main / root`

## 自定义指南

### 1. 头像
当前使用 `assets/img/profile.jpg`（600×900，约 72KB）。如需更换：
- 将新照片命名为 `profile.jpg` 覆盖 `assets/img/` 中的文件即可
- 建议竖版照片（2:3 或 3:4 比例），CSS 使用 `object-fit: cover` 自动适配

### 2. 修改邮箱
当前使用公开资料显示的 `dyy777@scut.edu.cn`（来源：哈尔滨工业大学 eHealth 实验室教师页，2018）。请确认是否仍为常用邮箱，全局搜索替换即可。

### 3. 补充论文条目
`publications.html` 中每组 `<ol class="pub-list">` 内按现有格式添加 `<li>` 即可。条目格式：
```html
<li><span class="pub-au">作者列表, <strong>Y. Dang</strong>.</span>
<span class="pub-ti">论文标题.</span>
<span class="pub-ve"><em>期刊名</em>, 卷(期): 页码, 年份.</span>
<span class="pub-lk"><a href="DOI链接" target="_blank">journal</a></span></li>
```
已标注「待补充」的位置（管理科学学报、Management Science 在审论文）拿到准确条目后替换。

### 4. 修改新闻 / 项目 / 课程
- News：`index.html` 中 `<ul class="news-list">` 内增删条目
- 项目卡片：`projects.html` 中 `.proj-grid` 内复制 `.proj-card` 块
- 课程：`teaching.html` 中复制 `.teach-item` 块

### 5. 配色
主色为深青色（teal，医疗+商务气质），定义在 `css/style.css` 顶部 `--theme` 变量；导航栏深藏青 `--nav-bg: #0d2438`。改一处变量即整站换色。

## 技术说明

- 纯 HTML + CSS + 少量原生 JS（深/浅色切换，记忆于 localStorage），零依赖、零构建
- 响应式布局（桌面双栏卡片 / 移动端单栏）
- 设计语言 adapted from [al-folio](https://github.com/al-folio/al-folio)（Kate 站点所用主题）
- 字体：Saira + 系统中文字体（Noto Sans SC 加载自 Google Fonts，离线时自动回退系统字体）
