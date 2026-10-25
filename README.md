# Han Zixu · Digital IC Verification Portfolio

一个无需构建工具、可直接部署到 GitHub Pages 的个人介绍与作品集静态网站。页面采用终端风格，支持中文 / English 切换，并如实标注当前学习、进行中和计划中的内容。

## 文件结构

```text
han-zixu-portfolio/
├── index.html      # 页面结构与文案
├── style.css       # 响应式终端视觉
├── script.js       # 中英文案表、语言切换与持久化、命令打字效果
└── README.md       # 本说明
```

## 联系方式（已配置）

`index.html` 的 `#contact` 区域已指向以下真实信息，如需更换请同时修改 `href` 与显示文字：

- GitHub：<https://github.com/kaohsiungcafe7259-prog>
- 邮箱：<mailto:zix_han@126.com>

建议只在有真实、可审阅的练习后，再将其仓库地址加入项目卡片；不要把计划中的练习写成已完成项目。

## 本地预览

直接双击打开 `index.html` 即可预览。也可以使用任意静态服务器打开该文件夹，例如：

```bash
python -m http.server 8000
```

然后访问 <http://localhost:8000>。

## 部署到 GitHub Pages

1. 登录 GitHub，点击右上角 **+** → **New repository**。
2. 仓库名称填 `kaohsiungcafe7259-prog.github.io`（个人主页地址会是 `https://kaohsiungcafe7259-prog.github.io/`）。
3. 选择公开仓库（Public）。不要勾选自动添加 README，以免与本项目文件冲突。
4. 若已在本地初始化 git（本仓库当前就是这种情况），只需把远端指向新仓库并推送：

   ```bash
   git remote add origin https://github.com/kaohsiungcafe7259-prog/kaohsiungcafe7259-prog.github.io.git
   git push -u origin main
   ```

   若还没有本地仓库，则将四个文件上传到仓库根目录：`index.html`、`style.css`、`script.js`、`README.md`，并提交（Commit）。
5. 打开仓库的 **Settings** → **Pages**。
6. 在 **Build and deployment** 中选择 **Deploy from a branch**；Branch 选择 `main`，文件夹选择 `/(root)`，然后点击 **Save**。
7. 等待 GitHub 完成发布。刷新 Pages 页面即可看到网站地址；首次部署通常需要几分钟。

若仓库使用其他名称，站点地址会变为 `https://kaohsiungcafe7259-prog.github.io/仓库名/`，相对路径仍可正常工作。

## 维护建议

- **改文案**：所有可切换的文本都在 `script.js` 的 `copy.zh` 与 `copy.en` 中，键名与 `index.html` 的 `data-i18n` 一一对应；新增键时两边都要加，缺一个会显示为空。
- **改样式**：`style.css` 为纯 ASCII 的多行文件，非 ASCII 图形（如列表前的 `›`）统一用 CSS 转义（`\203A`）书写，避免不同编辑器与工具链的编码问题。
- **状态标注**：每完成一项可复现练习，再更新对应的状态、说明和仓库链接；保持“进行中”“计划中”真实，成果经过自查后再标注为“已完成”。
- **响应式**：断点为 780px 与 420px；已适配 `prefers-reduced-motion`，动画会随系统设置关闭。
- GitHub Pages 使用相对文件路径，因此将这四个文件保留在同一目录即可正常部署。