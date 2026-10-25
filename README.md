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

   将 `width`、`height` 改为图片实际尺寸，`alt` 改为准确的英文描述。所有作品图片均使用 `width: 100%; height: auto`，按原始宽高比完整显示，不裁切包装主体。不要为真实图片添加固定高度或裁切比例。桌面首图横跨整行，后续作品使用双列；手机始终单列。
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


## 普洱茶项目案例

- 页面：`tea-packaging.html`，从首页 Pu’er tea 卡片的 “Read the case study” 进入。
- 结构：Project overview → My role → Design objectives → Design approach → Final presentation。
- 文案依据你提供的背景与职责整理。咖啡行业标准与国际化均写为目标，没有写成已经实现的标准、销量或成效。
- 案例使用作品图中可见的 PURE PU’ER TEA 名称；正式品牌命名仍可进一步确认。已接入三张作品原图；独立 Logo 原稿及更多物料可继续补充。

### 待补充资料

1. 正式品牌名、项目名称，以及项目属于商业、课程还是个人项目；年份可选。
2. 团队与协作情况、你负责的具体范围，尤其是包装结构、文案、摄影是否由你完成。
3. 调研发现：考察了哪些品牌或渠道，有哪些具体观察，哪些发现影响了最终方案。
4. 咖啡行业标准：具体借鉴了哪些方面，以及是否实际应用；未实施的部分应继续写为目标。
5. 视觉设计：Logo 的概念、色彩、字体、图形及各自选择依据。
6. 包装设计：茶叶品类、产品规格、容器或盒型、材料、工艺、结构，以及选择原因。
7. 最终成果：实际完成哪些包装、Logo 与广告物料；是设计稿、效果图、打样还是已生产。
8. 可展示的真实图片及说明；如有结果或反馈，仅填写可以确认的内容，没有则省略。

### 接入案例图片

把图片放进 `assets/`。在 `tea-packaging.html` 的 `.case-gallery` 中，将相应 `figure` 的 `.case-artwork-pending` 整个替换为 `<img class="project-image" ...>`，填写真实路径、准确英文 alt 和图片原始宽高，再更新 `figcaption`。图片使用原始比例完整显示。未提供的图片继续保留占位，不使用网页中的占位图形充当项目成果。


### 已接入的包装总览原图

从上传的 ZIP 中提取 PNG 原文件，保存为 `assets/pure-puer-tea-collection.png`，尺寸 1672 × 941。图片未裁切、重绘或重新压缩，首页首个作品、案例 Final presentation 和产品展示页均使用此原图。所有位置均以 `width: 100%; height: auto` 保留原始比例。

图片可见 PURE PU’ER TEA、Find Your Mountain、A Taste of the East，以及 Bingdao、Yiwu、Jingmai、Lao Ban Zhang 四款包装。案例依据图中内容描述四色区分、山形与植物图案、中英文字和编号。风味标签及刻度仅作为概念包装上的内容呈现。

### 产品展示页

`tea-collection.html` 从案例的 Final presentation → Explore the collection 进入。页面上方完整显示系列总览图，下方桌面双列、手机单列展示四款产品信息、风味标签、甜度/苦度刻度和可展开的 Discover；可通过 View full-size artwork 查看原图。

当前有三张系列展示图，但没有四款产品的独立图片，因此未重复图片或裁出不完整的包装主体。独立图片到位后可分别加入四个 `.collection-card` 顶部，使用 `<img class="project-image" ...>` 并填写准确的英文 alt 与原始宽高。作品图片保留自身色彩；网站界面橙色仅用于按钮、链接及其焦点。

正式品牌名确认、具体设计依据、独立 Logo、额外广告物料、材质工艺及生产状态仍待补充。参考前面的资料清单，原图现已接入，无需重复提交。


### 新增两张系列图

- `assets/pure-puer-tea-four-origins.png`：1024 × 1536，竖版 “Four Mountains. One Tea Ritual.” 展示图。
- `assets/pure-puer-tea-flavour-gift-box.png`：1536 × 1024，四色包装近景与开盒展示图。

两图均从上传 ZIP 中直接提取，未裁切、重绘或重新压缩。案例 Final presentation 现展示全部三张原图，替换原 Logo 与广告占位；这三张图不被称为独立 Logo 原稿。产品展示页以包装近景作为总览主图，并在四款产品信息后完整显示竖版展示图。首页使用首张横幅原图。手机与电脑均保留各图原始比例。
