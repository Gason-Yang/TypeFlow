# 字流 TypeFlow

Windows 本地打字训练工具，支持中文、英文、键位课程、成绩复盘，以及局域网内的竞赛和考试。

**免费使用，保留其他权利。** 本仓库提供产品说明和官方下载，不提供开源代码授权。使用前请阅读 [免费使用许可](LICENSE.txt)；第三方组件遵循各自许可证。

## 下载

打开 [最新版本下载页](https://github.com/Gason-Yang/TypeFlow/releases/latest)，在 **Assets** 中选择：

| 下载文件 | 适用场景 |
| --- | --- |
| [TypeFlow-standalone-win-x64.zip](https://github.com/Gason-Yang/TypeFlow/releases/latest/download/TypeFlow-standalone-win-x64.zip) | 每个人在自己的电脑上独立使用，数据各自保存 |
| [TypeFlow-lan-win-x64.zip](https://github.com/Gason-Yang/TypeFlow/releases/latest/download/TypeFlow-lan-win-x64.zip) | 一台 Windows 电脑作为主机，同一局域网内的其他电脑通过浏览器使用 |
| [SHA256SUMS.txt](https://github.com/Gason-Yang/TypeFlow/releases/latest/download/SHA256SUMS.txt) | 下载文件的 SHA-256 校验值 |

请选择上面两个 ZIP 中的一种。GitHub 自动提供的 Source code 压缩包仅包含本仓库说明文件，不是可运行软件。

## 快速开始

需要 Windows x64。便携包已包含 Node.js，无需另装 Node.js 或 npm。

1. 下载 ZIP，右键选择“全部解压”，放到可以写入的本地文件夹。
2. 单机版双击 `start.vbs`。浏览器会打开 `http://127.0.0.1:3210`。
3. 首次使用自行注册账号，首个注册账号成为管理员，没有预设账号或默认密码。
4. 使用结束后双击 `stop.vbs`。仅关闭浏览器不会停止后台程序。

不要直接在压缩包中运行，也不要双击 `web-dist/index.html`。

## 局域网主机版

1. 只在主机解压主机版，编辑 `lan-access.json`，填写允许访问的客户端 IPv4 地址。
2. 双击 `start-lan.vbs`，先在主机注册管理员。
3. 将启动提示中的主机地址交给同一局域网的使用者，使用者通过浏览器打开。
4. 修改白名单后先运行 `stop.vbs`，再重新启动。

发行包白名单为空，默认仅允许本机。详细步骤见包内 `LAN-ACCESS.txt`。主机需保持开机；仅用于可信局域网，HTTP 未加密，请勿做公网端口映射。程序不会自动更改防火墙。

## 功能

- 中英文打字、实时速度和准确率、逐字比对、暂停与续练。
- 键位课程、拼音和五笔指引、虚拟键盘、薄弱键位复盘。
- 自定义文章、TXT 导入、收藏、文章审核。
- 训练目标、历史成绩、CSV/JSON 导出。
- 本地账号、排行榜、竞赛、考试及考生名单导入。
- 日间/夜间界面，3D 双手指法提示。

## 数据与升级

账号、文章、消息和成绩保存在运行软件的电脑 `data/` 中；局域网模式统一保存在主机。

发行包不包含开发者数据库、账号、成绩、备份或实际 IP 白名单。运行后会创建使用者自己的数据。应用核心功能使用本地服务和本地资源。

升级前退出程序并备份，保留自己的 `data/`、`backups/`，主机版还要保留自己的 `lan-access.json`，不要用新包的空配置覆盖原有白名单。

备份时在程序目录运行 `runtime\node.exe backup.mjs`，一致性备份保存在 `backups/`。不要在程序运行时只复制 SQLite 主文件。

## 使用许可与反馈

允许个人使用及组织内部使用，允许调整正常运行配置以及管理和导出自己的数据。未授予修改软件代码、再分发、转售、再许可或对外提供托管服务的权利；可分享本项目官方页面和下载链接。完整条款以 [LICENSE.txt](LICENSE.txt) 为准。

Node.js 和其他第三方组件的许可证随下载包提供，第三方许可证赋予的权利不受 TypeFlow 原创部分许可的限制。

可通过 [Issues](https://github.com/Gason-Yang/TypeFlow/issues) 反馈问题。提交前请移除数据库、密码、Cookie、令牌、实际 IP 和其他个人信息。
