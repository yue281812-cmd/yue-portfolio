# Yue Shen — Personal Portfolio

个人作品集网站第一版。页面内容为英文，包含首页、作品展示、About 和 Contact；使用原生 HTML、CSS 和少量 JavaScript，支持手机和电脑，无需安装依赖或构建。

## 本地预览

在当前仓库执行：

```bash
cd /workspace/yue-portfolio
python3 -m http.server 8000 --bind 127.0.0.1
```

在支持访问该机器本地端口的浏览器中访问 `http://127.0.0.1:8000`。按 `Ctrl+C` 停止服务。云环境中的回环地址仅能在该环境内部访问；当前聊天界面不支持网站预览链接。也可将仓库下载到电脑，在仓库目录运行相同命令后浏览，或直接用浏览器打开 `index.html`。所有字体和页面资源均为本地资源，不依赖外部 CDN。

## 添加真实作品图片

1. 把具有使用权的图片放进 `assets/`，推荐 WebP、JPEG 或 PNG，文件名使用小写英文与短横线。建议图片宽度 1600–2400 像素，并压缩到合理大小。
2. 在 `index.html` 找到相应的 `<article class="project-card ...">`。将其中整个 `<div class="project-placeholder ...">...</div>` 替换为图片标签，例如（文件名仅为操作示例，当前文件不存在）：

   ```html
   <img class="project-image"
        src="assets/your-project.webp"
        alt="用英文准确描述此真实作品的内容"
        width="2000" height="1500"
        loading="lazy" decoding="async">
   ```

   将 `width`、`height` 改为图片实际尺寸，`alt` 改为准确的英文描述。首个大图在电脑上按 2:1 裁切，其他图片按 4:3 裁切；手机上均按 4:3 裁切。若需完整呈现图片，可在 CSS 中调整 `.project-image` 的 `object-fit` 或比例。
3. 修改该卡片的标题与 `Project to be added` 文案，只填入真实项目名称、类别及已确认的信息。尚未替换的卡片应保留占位标签。添加新作品时可复制现有卡片结构。
4. 所有占位图替换后，更新作品区说明及底部占位提示，使文字与实际内容一致。当前 CSS 图形仅用于布局占位，不能作为已完成项目展示。

## About 与联系方式

- 在 `index.html` 的 `#about` 区域补充真实英文个人介绍。
- `#contact` 当前只显示联系方式待补充，没有表单、虚构邮箱或社交账号。确认实际联系方式后再添加真实邮箱或社交链接。
- 当前页面没有客户、业绩或合作经历声明。

## 文件与检查

- `index.html`：页面结构与英文内容。
- `styles.css`：配色、排版、响应式布局与键盘焦点样式。
- `script.js`：手机导航开关、Escape 关闭和断点切换处理。
- `assets/`：存放后续作品图片。

可执行 `node --check script.js` 检查脚本语法。启动服务后检查各锚点、手机菜单、图片及桌面/手机布局。仓库目前没有自动化测试框架。

## 发布状态

网站已准备好通过 GitHub Pages 发布；是否上线以仓库 Settings → Pages 显示的部署状态为准。

发布设置：Source 选择 `Deploy from a branch`，Branch 选择 `main`，目录选择 `/ (root)`，点击 Save。等待 Pages 构建成功后，使用设置页给出的 Visit site 网址。默认预期地址为 `https://yue281812-cmd.github.io/yue-portfolio/`；在部署成功前，该地址可能返回 404。

仓库根目录包含 `.nojekyll`，页面无需构建。后续更新推送到 `main` 后，由 GitHub Pages 自动重新部署。上述 Python 命令仅用于本地预览。
