# Lesunny 临时网站

纯静态网站，发布目录为 `docs/`，无构建、外部字体或第三方脚本。

## 本地预览与修改

直接在浏览器打开 `docs/index.html`。修改该文件中的公司名称、标题和说明文字；样式在 `docs/styles.css`。

Logo 网页副本为 `docs/assets/lesunny-logo.jpg`，与根目录原件完全一致。替换时保留原件，更新网页副本、HTML 中图片的宽高（原始像素）及替代文字。CSS 使用 `height: auto` 保持比例。

## GitHub Pages 发布

正式网址：https://www.lesunny.com/ 。项目仓库：https://github.com/leo-aircon/lesunny-website 。Pages 使用 `main/docs`，自定义域名为 `www.lesunny.com`，Enforce HTTPS 已启用。

2026-10-29 验收：主网址 HTTPS 返回 200，裸域及 HTTP 地址均跳转到 HTTPS 主网址，Logo 和 CSS 返回 200，证书校验通过。桌面和手机布局已核验。域名验证 TXT 已配置，应长期保留；GitHub 账号内 Verify 按钮的最终状态未能自动读取。

1. 使用账号 `leo-aircon` 的公开仓库 `lesunny-website`。只上传本 README、`.gitignore` 和 `docs/` 中网站文件（含 GitHub 生成的 CNAME）。
2. 推送到 `main`。Settings → Pages → Deploy from a branch → `main` / `docs` → Save。
3. 在账号 Settings → Pages → Add a domain 验证 `lesunny.com`，将生成的专用 TXT 主机名和值记入本地变更单。此 TXT 长期保留。
4. 仓库 Settings → Pages → Custom domain 填 `www.lesunny.com` 并保存；GitHub 会在发布目录生成 CNAME 文件。拉取该提交，再修改 DNS。
5. 按本地 DNS 变更单配置解析，等待检查通过和证书签发，再勾选 Enforce HTTPS。
6. 验证 www 的 HTTPS、裸域跳转、HTTP 跳转、图片和邮箱记录。

后续更新：编辑 → 本地预览 → 按具体路径 `git add` → `git diff --cached --name-status` 检查 → 提交 → 推送。Pages 自动更新，等待部署成功后刷新正式网址。

禁止使用 `git add .` 或上传历史资料。根目录原始 Logo、历史资料及 `local-review/` 不进入仓库。DNS 备份仅保存在本地。

官方文档：
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
