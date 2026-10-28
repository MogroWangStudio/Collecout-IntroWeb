# 萃序 Collecout · 介绍页（Collecout IntroWeb）

「[萃序 Collecout](https://collecout.mogrowangstudio.top)」的官方网站与产品介绍页。萃序是一个**本地优先、开源**的信息提取与整理工具：导入 Word、Excel 和纯文本，自动分析结构、抽取字段，萃成可筛选、可检索、可导出的信息库。

- 产品主仓库与下载：<https://github.com/MogroWangStudio/Collecout>
- 工作室官网：<https://www.mogrowangstudio.top/>

## 这个仓库是什么

萃序的落地页（landing page），部署于 GitHub Pages，域名 `collecout.mogrowangstudio.top`。页面介绍萃序的核心特性并提供各平台下载入口。

**整个站点就是一个 `index.html`**：无框架、无构建、零运行时依赖，样式内联、脚本原生，克隆即改，推送即上线。

## 页面内容

- **特性介绍** —— 多格式导入与自动识别（标题层级、表格、`key: value` 行、段首日期）、模板系统（会议纪要 / 读书笔记 / 收支流水 / 通用表格，字段与提取方式可自定义）、表格与卡片双视图 + 空白处框选多选 + 组合筛选、Excel 单元格图片归档与放大预览、九种格式导出（含 Word / Excel / PDF / 图片 / 本地文件夹，图片随格式嵌入或随行携带）、本地存储与数据位置自定义
- **平台矩阵** —— 桌面端（Tauri 2，Windows / macOS / Linux）、Android（Capacitor 7，APK）、本地存储（「文件夹 + JSON」，不联网不上传）、界面（明暗双主题、字体预设与字号滑块）
- **下载区** —— 指向 GitHub Releases（Windows 便携版、macOS DMG、Android APK）与源代码仓库
- **中英双语** —— 右上角切换，选择记忆在 `localStorage`（键 `collecout-intro-lang`）

## 一些实现细节

- **顶栏** —— 滚动超过 5% 后收缩为一枚悬浮玻璃胶囊；下层内容通过渐变遮罩的背景模糊自然消隐
- **环境背景** —— 一层若隐若现的涟漪、一行自绘的 `key: value` 线条与一张自动组装的表格，纯 CSS 实现，`pointer-events: none`
- **无障碍与偏好** —— 完整响应 `prefers-reduced-motion` / `prefers-reduced-transparency` / `prefers-contrast`，语言菜单带焦点管理与 `aria` 标注
- **截图** —— 全部取自萃序 v1.4.0 真实界面（`npm run dev` 浏览器预览），演示数据由 `samples/` 示例文件导入生成

## 本地预览

无构建步骤，任意静态服务器即可：

```bash
# 仓库根目录下任选其一
python -m http.server 8000
npx serve .
```

然后打开 <http://localhost:8000>。

## 目录结构

```
.
├── index.html    # 全部页面（结构 + 样式 + 脚本）
├── CNAME         # GitHub Pages 自定义域名
└── assets/
    ├── collecout-logo.svg      # 萃序字标（顶栏）
    ├── collecout-mark.svg      # 萃序图形标
    ├── favicon.svg             # 站点图标
    ├── mogrowang-studio.svg    # 工作室字标（页脚）
    └── preview-*.png           # 产品截图
```

## 版本

采用**日期版本号**（`YYYYMMDD`），每次页面更新递增，明细见 [CHANGELOG.md](CHANGELOG.md)。当前版本：**20261028**，同时展示于页面页脚。

## 许可

代码以 [MIT License](LICENSE) 发布。© 2026 [MogroWang Studio](https://www.mogrowangstudio.top/)。
