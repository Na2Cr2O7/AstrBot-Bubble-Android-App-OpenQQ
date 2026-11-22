

## 🙏 致谢
感谢以下开源项目为本 App 提供基础支持：
 - [**AstrBot-Android-App**](https://github.com/zz6zz666/AstrBot-Android-App)：原版AstrBot项目
  - [**AstrBot-Bubble-Android-App**](https://github.com/MuFengDR/AstrBot-Bubble-Android-App)：原版AstrBot 泡泡版 项目
 - [**Code LFA**](https://github.com/nightmare-space/code_lfa)：提供安卓端 Ubuntu 容器环境
 - [**AstrBot**](https://docs.astrbot.app/)：强大的多平台聊天机器人框架
 - [**OpenQQ**](https://github.com/OpenQQ/OpenQQ)：当前 QQ 接入方案

 - ~~[**NapCatQQ**](https://napneko.github.io/guide/napcat)：旧版 QQ 接入方案~~ **删库了,代码保留用于兼容，入口已隐藏**


# 🫧 AstrBot 安卓 App-OpenQQ 版：让每一个普通人都能拥有自己的 AI 聊天机器人


在手机上可完整运行的QQ机器人。

只需要两部安卓手机，安装 App，等待应用启动完成，扫码登录 QQ，填入大模型密钥，就能让这个 QQ 号“活”起来。
>非常遗憾目前尚无在一台手机上扫码完成登录QQ的方法。~~但是你可以试试镜子+分屏~~

你可以用它：
- 让你和你的朋友们，都可以在 QQ 上和机器人账号一对一智能聊天
- 加入 QQ 群，与广大群友们一起互动；甚至借助庞大的 AstrBot 社区插件，实现各种有意思的功能
- 接入你喜欢的大语言模型（如 GPT、Deepseek、Gemini 等），让这个 QQ 账号拥有强大的对话能力

最关键的是：**这一切，不需要电脑、不需要懂命令行、不需要配置服务器。**


---

<p align="center">当然，这个软件是 【开源】 且 【免费】 的 ！！！

---

## 🛠️ 使用前必读：完整操作指南与注意事项

### 🌐 网络要求

 - `首次启动`必须在 **网络通畅的环境** 下进行  
 - 推荐使用 **家用 Wi-Fi 或手机 5G 流量**  
 - ❌ 避免使用校园网、公司内网、公共 Wi-Fi 等限速或受限网络，可能导致资源下载失败  

---

## 📲 **立即体验**  

下载release里面的最新安装包


### 🔧 初始化注意事项（请逐条阅读，以避免初始化失败）

1. **首次启动环境安装**  
 - 主页->环境管理 依次安装“基础命令”、“uv”、“OpenQQ”、“AstrBot”
 - 安装完成，点击刷新，图标右下显示绿色勾则安装成功

2. **强烈建议人工监视终端输出**  
 - 虽然过程自动化并可后台自动运行，但**强烈建议**在首次启动时切入**终端日志**页面，持续观察安装进度。  
 - 这样可以第一时间发现网络阻塞、下载失败等问题，避免长时间等待无果。

3. **OpenQQ 安装可能耗时较长**  
 - OpenQQ 会安装 Node 26、指定版本 Linux QQ、**g++/cmake/ninja 等编译工具**。Node 直接使用 nodejs.org 的 linux-arm64 压缩包，不再依赖 nvm/GitHub 安装脚本。首次安装时间较长，且对网络稳定性要求高。  
 - 若发现卡住或报错，可**直接关闭 App 再次启动**，系统会从中断处继续安装。

4. **安装中断可自动恢复**  
 - ✨ 新增稳健性优化：AstrBot 的代码仓库克隆已改为“原子操作”，避免因网络中断导致文件损坏。  
 - 初始化失败后重启，大部分情况下系统将自动恢复进程，大幅降低安装损坏风险。

5. **极端情况处理方式**  
 - 若多次重启仍无法完成初始化，可能是系统包损坏。  
 - 此时需进入手机设置 → 应用管理 → 找到 AstrBot App → **清除应用数据** → 重新启动。

6. **特例警告**  
 - 终端输出显示正在**安装系统软件包**（而非 uv、OpenQQ 等资源下载）时，请务必避免操作中断！！
 - 若终端出现如下提示：  
 `dpkg was interrupted, you must manually run 'dpkg --configure -a' to correct the problem`， 这表明系统软件包配置中断。虽然你可以按提示尝试修复，但建议你：
 **立即清除应用数据并重新初始化**。
    >修复的话大概10个小时以上吧~

1. **关于前台与息屏运行的说明**  
 - ✅ **首次初始化期间**：虽然理论上支持息屏、切换后台，但强烈建议**保持屏幕常亮**并**人工监视日志输出**，以便快速排查问题。  
 - ✅ **初始化完成后**：机器人可稳定在后台运行，息屏、切换 App 均不影响服务，只要保证通知栏**常驻通知**不被关闭即可。

### 🔄 登录与配置流程

完成初始化后，请按以下步骤操作：

1. **允许通知权限**  
 - 启动后 App 会请求通知权限，**必须点击“允许”**。  
 - ❌ 若拒绝，机器人将无法在后台持续运行。

2. **先启动 AstrBot**  
 - 主页点击“启动 AstrBot”，等待 WebUI 可以打开。  
 - OpenQQ 启动前会检查 AstrBot 是否已运行，并自动同步 aiocqhttp token。

3. **启动 OpenQQ 并扫码**  
 - 主页点击“启动 OpenQQ”，再点“登录画面”。  
 - 使用你手机上的 QQ 扫码登录；登录成功后卡片会显示账号，登录画面默认自动关闭。  
    >非常遗憾目前尚无在一台手机上扫码完成登录QQ的方法。
 - QQ 登录态会持久化，正常情况下重启 App / OpenQQ 后无需再次扫码。

4. **查看通知栏状态**  
 - 成功运行后，通知栏将显示“正在运行”常驻通知。  
 - 🔴 **禁止手动清除该通知**，否则服务将终止。

5. **首次登录控制台**  
 - **默认用户名和密码均为：`astrbot`**  
 - 登录后请按提示立即修改密码，确保账户安全。

6. **无需手动配置 OpenQQ 通信接口**  
 - OpenQQ 与 AstrBot 的 `aiocqhttp` 连接会由 App 自动维护，包括端口和 token。  
 - ❌ 不要手动修改 `/root/OpenQQ/config/openqq.json`，否则可能导致连接中断。

7. **填写大模型 API 密钥**  
 - 前往**模型提供商**页面，新增并填入你的模型服务商提供的 Token（API Key）。
 - **这是你唯一需要动手配置的地方，请自行搜索，或参考 AstrBot 官方[**文档**](https://docs.astrbot.app/)的 “接入大模型服务” 页面。**  
 - 支持 OpenAI、Anthropic、智谱、DeepSeek、Dify 等平台。  
 - 配置完成后保存并重启机器人即可。






## 架构
![alt text](arch2.jpg)


## ✅ 安卓 App 能做什么？不能做什么？

| 功能 | 是否支持 | 说明 |
|------|----------|------|
| 将你的 QQ 号变成 AI 机器人 | ✅ | 登录后即可自动收发消息，调用大模型回复 |
| 图形化配置界面 | ✅ | 内置 WebView，直接在手机上完成所有设置 |
| 接入多种大模型 | ✅ | 支持 OpenAI、Gemini、Dify、国产平台 API |
| 插件扩展功能 | ✅ | 可开启翻译、搜索、记忆等功能插件 |
| 后台稳定运行 | ✅ | 息屏、切后台不中断，消息实时响应 |
| QQ 富媒体消息 | ✅ | OpenQQ v0.4.0 已修复收图下载；部分大图/表情仍受上游限制 |
| QQ 多账号 | ❌ | 当前 OpenQQ 方案为单账号；旧 NapCat 多账号入口已隐藏 |
| 支持Telegram平台 | ❔  | 未测试 |
| 代码执行器 | ❌ | 代码沙箱的启用，依赖于 Docker 环境，安卓上的 ubuntu 容器默认未安装 |

<details> 

<summary>代码执行器</summary>

![alt text](arch_docker.jpg)

</details>


---


## 🫧 关于泡泡版？

本项目基于[**AstrBot-Android-App**](https://github.com/zz6zz666/AstrBot-Android-App)进行重构，解决了下面问题：
- 修复了启动卡在**配置中**的bug
- 安装分步进行，不再一次安装，减少出错概率。首次启动请在主页点击**环境管理**进行安装
- QQ 接入从 **删库的NapCat** 迁移到 OpenQQ，~~当前为单 QQ 账号~~由于QQ限制，一台Linux上面只能存在一个QQ实例。
- 优化了使用体验
- [**AstrBot-Android-App**](https://github.com/zz6zz666/AstrBot-Android-App)、 [**AstrBot-Bubble-Android-App**](https://github.com/MuFengDR/AstrBot-Bubble-Android-App) 和本项目三者均可共存
<details>
<p align="center">
<img src="logo-C2MGgWT2.png" width=50 />
<div align="center">晚安，NapCat</div>
<div align="center">2026.11.12</div>
</p>
</details>


---

## 🌐 什么是 AstrBot？

![455484170-ffd99b6b-3272-4682-beaa-6fe74250f7d9](https://github.com/user-attachments/assets/77a04df3-9721-4e92-b2c3-975c11006167)

[**AstrBot**](https://docs.astrbot.app/)：强大的多平台聊天机器人框架 是一个开源的多平台聊天机器人框架，专注于将大语言模型（LLM）接入日常社交工具（如 QQ、微信、Telegram），提供对话管理、插件扩展和自动化任务能力。其核心定位是 **“消息平台与大模型的连接器”**，支持多轮对话、知识库、代码执行器等高级功能。

### ✅ 原始项目核心能力

#### 🌐 多平台支持
- 兼容 **QQ（OneBot v11 / 官方版 均可）、微信（企业微信/公众号）、飞书、钉钉、Telegram、Discord** 等 15+ 平台。
- 支持多实例部署，可同时运行多个机器人账号。
- 提供消息过滤、白名单、速率限制等管理功能。

#### 🤖 大模型对接
- 支持主流大模型：**GPT、Google Gemini、DeepSeek、GLM、千问** 等。
- 兼容本地部署方案（如 Ollama、llama.cpp），降低 API 成本。
- 支持多模型混合调用、负载均衡、失败自动切换。

#### 🤹 Agent 任务自动化
- **代码执行器**：在安全沙箱中运行 Python/JS 代码并返回结果。
- **网页搜索**：实时联网获取最新信息，回答时效性问题。
- **待办事项**：自然语言解析并管理任务列表。
- **记忆系统**：长期记忆用户偏好与历史对话上下文。

#### 🧩 插件扩展系统
- 内置官方插件：天气查询、翻译、知识问答、数学计算、图片生成等。
- 支持开发者自定义插件（Python 编写），社区生态丰富。
- 插件可独立开启/关闭，完全模块化设计。

#### 🖥️ 开发者友好
- 基于事件总线和流水线架构，易于二次开发。
- 提供完整的 RESTful API 和 WebSocket 接口。
- 支持 Docker、Windows、Linux 多种部署方式。

> 📌 **一句话总结**：  
> AstrBot 是一个功能强大、高度可扩展的 AI 机器人开发框架，适合开发者、极客用户构建专业级聊天机器人。

## 🧭 什么是 OpenQQ？


<div align=center>

<img src="https://github.com/feijx3/OpenQQ/raw/main/web/logo.svg" width=150 />
<div style="margin:2em"></div>
</div>



**[OpenQQ](https://github.com/feijx3/OpenQQ)** 是一个由开发者 **feijx3** 创建的**项目**。核心作用是为 Windows 和 Linux 上的 QQ NT 客户端提供一个 **OneBot v11 标准的桥接**，让开发者能通过标准接口来开发QQ机器人或进行自动化操作。

以下是关于它的关键信息整理：

### 🛠️ 核心功能与特性
OpenQQ 提供了一整套机器人开发和管理工具：
- **OneBot v11 桥接**：支持正向 WebSocket 服务端（带鉴权）和反向 WebSocket 客户端（最多8个目标）。
- **丰富的消息与操作**：支持发送文本、图片、语音、视频、文件等，以及撤回、禁言、踢人、处理好友/群申请等管理操作。
- **内置 WebUI 控制台**：默认监听本地，提供概览、消息收发、事件流、动作调试、日志查看等功能。
- **图形化 Bot 编辑**：在 WebUI 中可通过拖拽"积木"的方式搭建机器人逻辑，并能接入 OpenAI 兼容的 AI 接口。
- **Docker 部署**：内置 Dockerfile 和 compose 文件，支持无头扫码和滑块登录。

### 💻 技术实现方式
它的实现方式比较"底层"且克制：
- **Windows**：通过 C++ 原生启动器，在 QQ 注册原生模块的位置（`qq_magic_napi_register`）**挂接会话**，不开启 Electron 的 `--inspect` 端口，也不修改 QQ 安装目录中的文件。
- **Linux**：**使用 `LD_PRELOAD` 预加载引导库，在加载目标 `wrapper.node` 时注入会话。**
- **主体逻辑**：OneBot、WebUI 和会话逻辑均由 Node.js / JavaScript 实现。

### 📋 环境要求
- **Windows**：Windows 10 / 11 x64，QQ NT 9.x（已测试 `9.9.33-52230` 和 `9.9.37-54395`）。
- **Linux**：x64 / arm64 架构。
> 📌 **一句话总结**：      
> OpenQQ 是一个技术实现精巧的**QQ机器人开发框架**。






---



---

## 🧱 从源码编译

项目包含 `normal` 和 `profileTest` 两个 product flavor。编译时必须显式指定 flavor，否则 Flutter 会因找不到默认的 `app-release.apk` 而报 `Gradle build failed to produce an .apk file`（实际上 APK 已生成，只是文件名带 flavor 后缀）：

```bash
flutter pub get
flutter build apk --release --flavor normal
```

产物位于 `build/app/outputs/flutter-apk/app-normal-release.apk`。

---



## 许可证说明 📜

本项目分成两个独立组件：

- **App 本体**：BSD-3-Clause，见根目录 `LICENSE`
- **OpenQQ**：AGPL-3.0，安装时从上游仓库获取，不打包进 APK

第三方许可证、OpenQQ 版本与修改说明见：

- [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md)
- [`LICENSES/AGPL-3.0.txt`](LICENSES/AGPL-3.0.txt)
- [`LICENSES/BSD-3-Clause.txt`](LICENSES/BSD-3-Clause.txt)

App 内“设置 → 开源许可”也可以查看完整文本。

如果后续把 OpenQQ 源码或二进制直接打进 APK，需要重新评估整体分发方式，通常应把整体按 AGPL-3.0 发布。

---

## 反馈交流

- 如果你在使用过程中遇到问题或有功能建议，欢迎提交 Issues 或参与项目讨论！ 💬🌟

> （注：本文档部分内容由 AI生成）



