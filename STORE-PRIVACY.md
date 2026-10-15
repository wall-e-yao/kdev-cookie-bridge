# Chrome Web Store 隐私字段 — KS Cookie Bridge 1.0.2

## 单一用途说明

为配套研发页面提供 kuaishou.com、gifshow.com 及其子域和 localhost 的 Cookie 查询桥接能力。页面指定 URL 或域名，扩展查询获授权范围内的 Cookie 并返回结果。需要配套页面及相应平台账号和网络访问条件。提交前还应补充实际用户可见的业务功能及操作入口。

## 需请求 cookies 的理由

扩展使用 chrome.cookies.getAll 按 URL 或域名读取 Cookie，并返回给请求页面。该 API 需要 cookies 权限。结果可能包括会话和认证凭证，访问及交付方式已在隐私政策披露。扩展不调用 Cookie 写入或删除 API。

## 需请求主机权限的理由

Chrome Cookie API 需要对应站点的主机权限。本版本申请 kuaishou.com、gifshow.com 及其子域和 localhost，并在这些匹配页面加载查询桥接脚本。kuaishou.com 与 gifshow.com 用于配套站点的 Cookie 查询；localhost 用于本地配套页面及开发调试。localhost 不自动包含 127.0.0.1。应结合实际业务确认能否进一步收窄到具体主机。

## 远程代码

选择“不，我并未使用远程代码”。background.js、content.js、getCookies.js 均包含在包内。getCookies.js 通过 chrome.runtime.getURL 引用。

## 数据使用

身份验证信息：应披露。个人身份信息：如果实际 Cookie 包含账号 ID、邮箱等，需要披露。本版本不按 Cookie 名称过滤，需核实真实返回内容。

没有浏览历史 API 调用，不能仅因 Cookie 读取就声明采集完整浏览历史。网络记录、网站内容、位置及其他类型，需结合实际 Cookie、URL 记录与网页数据流判断。

三项数据使用承诺必须真实才能勾选。扩展自身无售卖、广告定向、信用或贷款功能，配套业务后续用途、接收方和保留期限仍需网站运营方确认。没有独立上传接口不代表网页不上传。

## 隐私政策网址

网页：https://wall-e-yao.github.io/kdev-cookie-bridge/privacy.html

备用 Markdown：https://github.com/wall-e-yao/kdev-cookie-bridge/blob/main/PRIVACY.md

仅在地址验证可公开访问后填写。

