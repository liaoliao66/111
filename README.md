# 武穴多式联运大屏 — Screen2 / Screen3 发布包

本目录为**可独立发布**的静态站点，包含：

| 文件 | 说明 |
|------|------|
| `index.html` | 访问入口（链接到两个大屏） |
| `screen2.html` | 细节展示屏 / 运营专题屏 |
| `screen3.html` | 集装箱运营专题屏 |
| `vendor/` | ECharts、Font Awesome（离线） |
| `assets/` | 港区底图等资源 |
| `screen2-doc.md` / `screen3-doc.md` | 数据说明文档 |

## 本地预览

1. 保持本目录结构不变（`screen2.html` 与 `vendor` 同级）。
2. 双击 `index.html`，或分别打开 `screen2.html`、`screen3.html`。
3. 推荐使用 Chrome / Edge。

## 发布到 GitHub（一条链接访问）

### 方式 A：本目录作为仓库根目录（推荐）

1. 在 GitHub 新建仓库（例如 `wuxue-display-wall`）。
2. 将 **`publish` 文件夹内的全部内容** 推送到仓库**根目录**（不是把整个 `Display_Wall` 推上去，除非你想保留其它文件）。
3. 仓库 → **Settings** → **Pages**：
   - **Source**：Deploy from a branch
   - **Branch**：`main`（或 `master`） / **Folder**：`/ (root)`
4. 保存后等待 1～3 分钟，访问：

   **本仓库访问地址：**

   `https://liaoliao66.github.io/111/`

5. 各屏直链：
   - 入口：`https://liaoliao66.github.io/111/`
   - 细节屏：`https://liaoliao66.github.io/111/screen2.html`
   - 集装箱屏：`https://liaoliao66.github.io/111/screen3.html`

### 方式 B：放在 monorepo 子目录

若必须把整个 `Display_Wall` 推送到 GitHub，可在仓库根目录配置 Pages 的 **子路径**，或把 `publish` 内容复制到仓库根目录后再启用 Pages。

### 推送命令示例

```bash
cd publish
git init
git add .
git commit -m "发布 screen2/screen3 大屏静态站点"
git branch -M main
git remote add origin https://github.com/liaoliao66/111.git
git push -u origin main
```

## 目录结构

```
publish/
├── index.html
├── screen2.html
├── screen3.html
├── screen2-doc.md
├── screen3-doc.md
├── README.md
├── vendor/
│   ├── echarts.min.js
│   └── font-awesome/
│       ├── css/
│       └── webfonts/
└── assets/
    └── port-map.svg
```

## 说明

- 页面数据为前端演示数据，联调时按文档替换接口。
- 图标依赖 `vendor/font-awesome/webfonts`，打包时已包含常用字体文件。
- `screen2` 港区图默认 `assets/port-map.svg`；若有高清 PNG，可放入 `assets/port-map.png` 作为备用。
