# 北京两日行程 H5 项目记录

## 已完成
- ✅ HTML 行程页面制作，适配移动端
- ✅ 部署到 GitHub Pages，获得公网可访问链接
- ✅ 微信内置浏览器直接打开，无需跳转外部浏览器
- ✅ 绑定自定义域名 `www.blackest.top`
- ✅ 添加 Open Graph meta 标签，支持微信卡片分享

## 当前状态
- 页面地址：`https://www.blackest.top/beijing-trip-h5.html`
- GitHub Pages 地址：`https://renkai153.github.io/beijing-trip/beijing-trip-h5.html`
- 微信打开有小卡片，顶部仍有"非官方页面"提示（需备案解决）

## 后续优化计划（阿里云 + 备案）

### 第 1 步：备案准备
- 域名 `blackest.top` 已实名认证，等待 3 天后可提交备案
- 在阿里云提交 ICP 备案（预计 7-20 个工作日）

### 第 2 步：迁移到阿里云
方案二选一：

**方案 A：阿里云 OSS 静态托管（推荐，最便宜）**
- 创建杭州/上海地域的 OSS Bucket
- 开启静态网站托管
- 上传 HTML 文件
- 绑定已备案的域名，开启 HTTPS

**方案 B：阿里云 ECS 服务器**
- 购买轻量应用服务器
- 用 Nginx 做静态文件服务

### 第 3 步：微信生态优化
- 备案完成后，微信"非官方页面"提示自动消失
- 配置微信 JS-SDK，实现自定义分享标题/描述/图片

## 更新页面的命令
```bash
git add beijing-trip-h5.html
git commit -m "更新内容描述"
git push
```

## 本次踩坑记录
1. 微信分享卡片不出：加 `og:*` meta 标签，用 `?v=` 参数清缓存
2. 微信卡片 100% 出的方法：点开页面 → 右上角 `...` → 发送给朋友
3. GitHub CLI 安装后路径问题：需要用 `"C:\Program Files\GitHub CLI\gh.exe"` 完整路径
4. git push 被拒绝：用 `git push -f` 强制覆盖（单人项目安全）
