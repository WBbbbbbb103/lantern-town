# 上传到 GitHub 的操作说明

这份说明是写给接手上传工作的 AI / 操作者的。

## 要上传哪些文件

上传 **本目录中的全部内容** 到 GitHub 仓库的**根目录**，不要多套一层文件夹：

```text
index.html
README.md
UPLOAD.md
THIRD_PARTY_NOTICES.md
.nojekyll
.gitignore
screenshots/
```

注意：

- `index.html` 必须位于仓库根目录。它是完整的单文件站点（约 1 MB），不需要构建。
- `.nojekyll` 是隐藏文件，上传时容易被遗漏；GitHub Pages 需要它来绕过 Jekyll 处理。
- 不要上传外层工作目录、`_town/`、`_build/`、测试脚本、Edge profile 或截图原始 PNG。
- 不要修改 `index.html` 的内容。

## 推荐仓库信息

- **仓库名**：`lantern-town`（或 `dengting`）
- **描述**：`灯町 · Lantern Town — 一座放在桌面上、会自己生活的 3D 微缩小镇`
- **Topics**：`threejs`, `webgl`, `creative-coding`, `interactive-art`, `miniature`, `generative-art`, `single-file`
- **Social preview**：上传 `screenshots/dusk.jpg`
- **默认分支**：`main`

## Git 命令行

在包含本说明的目录里执行：

```bash
git init
git checkout -b main
git add -A
git commit -m "feat: add Lantern Town interactive miniature"
git remote add origin https://github.com/<用户名>/<仓库名>.git
git push -u origin main
```

如果目标仓库已经存在，请不要重复初始化；进入该仓库工作区后，将上述文件复制到根目录，再提交和推送。

## 开启 GitHub Pages

1. 打开仓库的 **Settings → Pages**。
2. **Build and deployment → Source** 选择 `Deploy from a branch`。
3. Branch 选 `main`，目录选 `/(root)`。
4. 保存，等待 1–2 分钟。
5. 访问 `https://<用户名>.github.io/<仓库名>/`。

如果仓库是私有的，GitHub Pages 可能需要付费计划；发布前应先和用户确认仓库可见性。

## 发布前检查

- [ ] 仓库根目录能看到 `index.html`。
- [ ] Pages 地址返回 200，页面显示「灯町」开场页。
- [ ] 点击「推门进去」能进入小镇，场景可见。
- [ ] 按住拖动可以转动，滚轮/双指可以靠近，点击喷泉会出现气泡。
- [ ] `R` 或底栏云朵能唤雨，街道和行人会进入雨天的状态。
- [ ] 在手机尺寸下页面不横向溢出，底栏按钮可用。
- [ ] 浏览器控制台没有致命错误。Three.js 的 UMD 弃用提示是预期内的 warning。

## 许可提醒

Three.js 的 MIT 许可见 `THIRD_PARTY_NOTICES.md`。除此之外，本仓库没有附默认开源许可证；除非用户明确要求，不要自行添加 `LICENSE` 或更改仓库可见性。
