# 碎银几两 · v12 GitHub 交互体验版 2

这是可直接放到 GitHub Pages 的静态网页，无需安装依赖或编译。

## 体验范围

钱包展开、渠道切换、银行卡添加与删除、年度合计、翻页账本、月份书签、添加/编辑/删除测试账目、内部互转、文件导入与导出均可体验。
每次进入默认生成两张虚构体验银行卡（0000 / 8888），初始账目为空，不代表真实账户。
新增约2.1秒开屏：钱币落入束口袋、轻轻收口后进入页面；支持跳过、Esc与系统减少动态效果。
“填入示例”加入 5 笔明确标为示例的虚构账目，不覆盖已添加记录；“重新体验”清空当前体验。

## 数据边界

- 测试数据只在当前网页的 JavaScript 内存中；刷新、关闭或重新打开即清空。
- 不使用 localStorage、sessionStorage、IndexedDB、Cookie 或 Service Worker 保存数据。
- 没有登录、账号、云同步、访客统计或主动上报；CSP 禁止页面向服务端发送数据连接。
- 导入仅在本页解析，导出仅在用户主动点击后生成本机文件；不要使用真实账单、银行卡号或身份信息。
- GitHub Pages 作为托管平台仍会处理访问请求和平台日志；本网页没有额外收集访客数据。
- GitHub 仓库和页面若设为公开，任何获得地址的人都可能访问；请只上传本文件夹内容。

## 上传与发布

1. 在 GitHub 新建一个空的公开仓库，例如 suiyin-preview。
2. 用 Upload files 上传本文件夹内的文件（空仓库可点 uploading an existing file）；确保 index.html 在仓库根目录，icons/、libs/ 目录结构不变。README.md 可一同上传；.nojekyll 若界面未显示可省略，本包不依赖下划线目录。
3. 在 Settings → Pages 中选择 Deploy from a branch，分支 main、目录 / (root)，保存。
4. 等待部署完成，使用 Pages 显示的 HTTPS 地址分享；手机直接用 Safari 或 Chrome 打开即可。

本包包含 10 个文件。不要把整个外层文件夹再套在仓库根目录，不要上传原工作台、私人备份或本机配置。
未上传 GitHub，未修改原 v12、正式站点或真实账目。

发布步骤已参照 [GitHub Pages 官方文档](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) 核对。

## 已完成的本地验证

v2 新增验证：进入默认展示两张虚构体验卡，刷新后恢复两张卡但账目为空；填入示例不产生第三张卡。约 2.1 秒开屏自动结束，跳过、Esc、减少动态效果及 320px 布局通过；束口形变与钱币落袋已检查关键画面。

WebKit 320 / 390 / 986px 与 Chromium（Edge）390px 已验证示例、渠道切换、翻页、年度金额、账目增改删、取消/确认删卡、JSON 导入导出、刷新清空和重新体验；未发现脚本错误、缺失资源、外部请求或横向溢出。Chromium 另验证独立标签页隔离、持久存储调用为零和双击 HTML 打开。未进行真实 iPhone 或 GitHub 线上验收。

## 第三方组件

翻页效果使用内嵌 StPageFlip 2.0.7（MIT），许可见 libs/page-flip-LICENSE.txt。
文件解析沿用原项目的 JSZip、SheetJS 与 PDF.js 本地依赖及其文件内许可声明。
