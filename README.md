<p align="center">
  <a href="#cad-viewer">English</a> &nbsp;|&nbsp;
  <a href="#中文说明">中文</a> &nbsp;|&nbsp;
  <a href="#-support"><img src="https://img.shields.io/badge/☕-Support-orange?style=flat-square" /></a>
  <a href="#打赏"><img src="https://img.shields.io/badge/💰-打赏-red?style=flat-square" /></a>
</p>

---

# CAD Viewer

> Preview **.dxf** and **.dwg** CAD drawings directly inside your Obsidian notes — no external CAD software, no leaving the app.

A lightweight Obsidian desktop plugin that embeds the [mlightcad/cad-viewer](https://github.com/mlightcad/cad-viewer) viewer into your vault. Open any supported drawing file and it renders in-place with WebGL, pan/zoom, and layer-aware rendering.

<div align="center">
  <img src="https://github.com/user-attachments/assets/b1b91eaa-1142-47fd-8f0c-a2866a179c30" alt="CAD Viewer in-note preview" />
</div>

**V1.0.0** — Core release:
- **In-note DXF/DWG preview** — double-click a `.dxf` / `.dwg` file and it opens inside the note, not in AutoCAD / your OS default app
- **Self-contained 3-file release** — the ~14 MB of parser workers (including the LibreDWG WASM) are inlined into `main.js`, so a plain community release (`manifest.json` + `main.js` + `styles.css`) works with zero extra downloads
- **Fast parse** — larger worker chunk size reduces round-trips for big DWG files

---

## Features

| Feature | Detail |
|---------|--------|
| 📐 **DXF preview** | Open AutoCAD / compatible DXF drawings directly in reading view |
| 🏗️ **DWG preview** | Full `.dwg` support via the LibreDWG converter (runs in a Web Worker) |
| 🖱️ **Interactive canvas** | Pan, zoom, and inspect drawings with the built-in Three.js / WebGL viewer |
| 🖥️ **Desktop only** | Uses Electron's Web Worker + file APIs; not available on Obsidian mobile / web |

> **Note on DWG:** DWG parsing relies on [LibreDWG](https://www.gnu.org/software/libredwg/), which is distributed under **GPL-3.0**. Because of this dependency, the whole plugin is released under **GPL-3.0** (see [License](#license)).

---

## Installation

### From GitHub (Manual)

1. Go to [Releases](https://github.com/liamzy2021/obsidian-cad-viewer/releases) and download the latest `main.js`, `manifest.json`, and `styles.css`
2. Create a folder named `cad-viewer` in your vault's `.obsidian/plugins/` directory
3. Copy all 3 files in:
   ```
   .obsidian/plugins/cad-viewer/
   ├── main.js
   ├── manifest.json
   └── styles.css
   ```
4. Restart Obsidian or reload plugins
5. Go to **Settings → Community Plugins → Enable "CAD Viewer"**

> ⚠️ The folder **must** be named `cad-viewer` (matching the plugin `id`). A differently named folder will not be recognized by Obsidian.

### From Community Plugins

1. Open **Settings → Community Plugins → Browse**
2. Search for "CAD Viewer"
3. Click **Install**, then **Enable**

---

## Usage

- **Open a drawing** — Double-click any `.dxf` or `.dwg` file in the file explorer; it opens inside the note instead of handing off to your OS default app
- **Navigate** — Scroll / drag to pan, pinch or wheel to zoom
- **Close** — Switch to another note or file as usual

---

## Requirements

- Obsidian **1.4.0** or later (desktop app)
- **Desktop only** — the plugin depends on Electron's Web Worker and file-system adapter; it will not load on mobile or the web client

---

## License

**GPL-3.0**

This plugin bundles the LibreDWG-based DWG converter (`@mlightcad/libredwg-*`), which is licensed under GPL-3.0. Under the terms of the GPL, this plugin as a whole is also GPL-3.0. You are free to use, modify, and redistribute it, provided you keep the source available under the same license.

---

## Author

**栗子仁儿 (liamzy2021)** · [GitHub](https://github.com/liamzy2021)

---

## ☕ Support

If this plugin saves you from alt-tabbing into a CAD app, feel free to support its development:

<div align="center">
  <table>
    <tr>
      <td align="center" width="240">
        <a href="https://paypal.me/lilirenzy" target="_blank" rel="noopener">
          <img src="https://img.shields.io/badge/💳-PayPal-003087?style=for-the-badge&logo=paypal&logoColor=white" />
        </a>
        <br/><b>PayPal</b>
      </td>
      <td align="center" width="240">
        <a href="https://ko-fi.com/liamzy" target="_blank" rel="noopener">
          <img src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="36" alt="Buy Me a Coffee at ko-fi.com" />
        </a>
        <br/><b>Ko-fi</b>
      </td>
    </tr>
  </table>
</div>

---

<a name="中文说明"></a>

# 中文说明

> 在 Obsidian 笔记内**直接预览 .dxf 和 .dwg 图纸**——无需安装 CAD 软件，无需离开应用。

一款轻量级的 Obsidian 桌面插件，把 [mlightcad/cad-viewer](https://github.com/mlightcad/cad-viewer) 查看器嵌入你的仓库。打开任意支持的图纸文件，即可用 WebGL 在原地渲染，支持平移、缩放与图层感知显示。

<div align="center">
  <img src="https://github.com/user-attachments/assets/b1b91eaa-1142-47fd-8f0c-a2866a179c30" alt="CAD 查看器笔记内预览" />
</div>

**V1.0.0** — 首个正式版：
- **笔记内 DXF/DWG 预览** — 双击 `.dxf` / `.dwg` 文件，直接在笔记内打开，而不是用 AutoCAD / 系统默认软件打开
- **自包含三文件发布** — 约 14MB 的解析 Worker（含 LibreDWG WASM）已内联进 `main.js`，标准社区发布包（`manifest.json` + `main.js` + `styles.css`）无需任何额外下载即可使用
- **解析加速** — 更大的 Worker 分块，减少大 DWG 文件的往返次数

---

## 功能特性

| 功能 | 说明 |
|------|------|
| 📐 **DXF 预览** | 在阅读视图中直接打开 AutoCAD / 兼容的 DXF 图纸 |
| 🏗️ **DWG 预览** | 通过 LibreDWG 转换器（运行于 Web Worker）完整支持 `.dwg` |
| 🖱️ **交互画布** | 用内置的 Three.js / WebGL 查看器平移、缩放、查看图纸 |
| 🖥️ **仅桌面端** | 依赖 Electron 的 Web Worker 与文件系统 API，Obsidian 移动端 / 网页端不可用 |

> **关于 DWG 的说明：** DWG 解析依赖 [LibreDWG](https://www.gnu.org/software/libredwg/)，其许可证为 **GPL-3.0**。正因如此，本插件整体以 **GPL-3.0** 发布（见[许可证](#许可证)）。

---

## 安装

### 从 GitHub 手动安装

1. 前往 [Releases](https://github.com/liamzy2021/obsidian-cad-viewer/releases) 下载最新的 `main.js`、`manifest.json` 和 `styles.css`
2. 在 Obsidian 仓库的 `.obsidian/plugins/` 目录下新建 `cad-viewer` 文件夹
3. 将 3 个文件复制进去：
   ```
   .obsidian/plugins/cad-viewer/
   ├── main.js
   ├── manifest.json
   └── styles.css
   ```
4. 重启 Obsidian 或重新加载插件
5. **设置 → 社区插件 → 启用 "CAD Viewer"**

> ⚠️ 文件夹**必须**命名为 `cad-viewer`（与插件 `id` 一致）。名字不对 Obsidian 不会识别。

### 从社区插件商店安装

1. 打开 **设置 → 社区插件 → 浏览**
2. 搜索 "CAD Viewer"
3. 点击 **安装**，然后 **启用**

---

## 使用说明

- **打开图纸** — 在文件浏览器中双击任意 `.dxf` 或 `.dwg` 文件，会在笔记内打开，而不是交给系统默认软件
- **浏览** — 滚动 / 拖拽平移，滚轮或双指缩放
- **关闭** — 像平时一样切换到其他笔记或文件即可

---

## 系统要求

- Obsidian **1.4.0** 或更高版本（桌面端）
- **仅桌面端** — 插件依赖 Electron 的 Web Worker 与文件系统适配器，移动端 / 网页端无法加载

---

## 许可证

**GPL-3.0**

本插件集成了基于 LibreDWG 的 DWG 转换器（`@mlightcad/libredwg-*`），其许可证为 GPL-3.0。根据 GPL 条款，本插件整体同样以 GPL-3.0 发布。你可以自由使用、修改和再分发，但需以相同许可证保持源码开放。

---

## 作者

**栗子仁儿 (liamzy2021)** · [GitHub](https://github.com/liamzy2021)

---

<a name="打赏"></a>

## 💰 打赏

如果这个插件帮你省去了切来切去开 CAD 软件的麻烦，欢迎打赏支持！

<div align="center">
  <table>
    <tr>
      <td align="center" width="280">
        <a href="https://ifdian.net/a/liamzy2021" target="_blank" rel="noopener">
          <img src="https://static.afdiancdn.com/static/img/logo/logo.png" width="80" alt="爱发电 Afdian" />
          <br/>
          <b>❤️ 前往爱发电支持</b>
        </a>
      </td>
      <td align="center" width="280">
        <img src="https://github.com/user-attachments/assets/a1065a8d-2844-4765-b45f-403f23348d84" width="200" alt="微信赞赏" />
        <br/>
        <b>微信赞赏</b>
      </td>
    </tr>
    <tr>
      <td align="center" width="280">
        <a href="https://paypal.me/lilirenzy" target="_blank" rel="noopener">
          <img src="https://img.shields.io/badge/💳-PayPal-003087?style=for-the-badge&logo=paypal&logoColor=white" />
          <br/>
          <b>PayPal</b>
        </a>
      </td>
      <td align="center" width="280">
        <a href="https://ko-fi.com/liamzy" target="_blank" rel="noopener">
          <img src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="36" alt="Buy Me a Coffee at ko-fi.com" />
          <br/>
          <b>Ko-fi</b>
        </a>
      </td>
    </tr>
  </table>
</div>
