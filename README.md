# 安全运维工具箱 SSKit

[![Release](https://img.shields.io/github/v/release/nbyiansec/sskit?label=release&color=green)](https://github.com/nbyiansec/sskit/releases)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20Docker-blue)](#快速开始)
[![Bilibili](https://img.shields.io/badge/video-Bilibili-ff69b4)](https://www.bilibili.com/video/BV1rzTTzsEB3/)
[![License](https://img.shields.io/badge/license-Freeware-orange)](LICENSE)
[![Stars](https://img.shields.io/github/stars/nbyiansec/sskit?style=social)](https://github.com/nbyiansec/sskit/stargazers)

面向企业安全运维团队的一体化工具集 —— 从资产梳理到漏洞闭环，从配置核查到批量运维，一个平台搞定。

> **v1.0.6 已发布：新增互联网资产搜索**
> 新增「互联网搜索」任务类型，支持「查企业」「查 IP/域名」，接入鹰图、夸克引擎；网站扫描新增鹰图、Quake 多引擎测绘；「网络空间」更名为「项目空间」。
> 下载地址：<https://github.com/nbyiansec/sskit/releases>

## 目录

- [简介](#简介)
- [功能特性](#功能特性)
- [快速开始](#快速开始)
  - [Windows 部署](#windows-部署)
  - [Linux 部署](#linux-部署)
  - [Docker 部署](#docker-部署)
- [常见问题](#常见问题)
- [更新日志](#更新日志)
- [反馈与支持](#反馈与支持)
- [致谢](#致谢)
- [授权许可](#授权许可)
- [免责声明](#免责声明)
- [关于我们](#关于我们)
- [联系我们](#联系我们)

## 简介

安全运维工具箱是一款面向安全运维场景的集成化利器，融合了资产管理、资产测绘、漏洞检测、配置核查、弱口令检测、批量化运维、漏洞跟踪、报告生成以及日志审计等核心功能模块，实现安全运维服务的标准化、自动化，助力用户构建高效、精准、可复用的安全运维体系。

> 本软件为**免费使用（非开源）**软件，可免费下载、安装和使用。本仓库仅提供程序包、部署配置与使用文档，**不包含应用源代码**。

[![功能演示视频](assets/0.png)](https://www.bilibili.com/video/BV1rzTTzsEB3/)

功能演示视频：<https://www.bilibili.com/video/BV1rzTTzsEB3/>

系统工作台：

![工作台](assets/13.png)

## 功能特性

### 1. 资产管理

提供主机和应用资产的全生命周期管理，支持资产录入、批量导入、批量属性变更、资产打标、状态追踪（新增/变更/下线）、资产导出等功能。基于资产管理的安全检测服务体系，以资产为中心开展各项安全检测服务（资产测绘、配置核查、弱口令检测、漏洞检测等），通过多源数据融合构建多维资产档案。

![资产管理](assets/1.png)

<p align="center">
  <img src="assets/14.png" alt="应用资产管理" width="49%" />
  <img src="assets/15.png" alt="应用资产详情" width="49%" />
  <img src="assets/16.png" alt="主机资产管理" width="49%" />
  <img src="assets/17.png" alt="主机资产详情" width="49%" />
</p>

### 2. 漏洞管理

提供漏洞的全生命周期管理，涵盖漏洞的发现、评估、修复、验证、记录、统计分析等，同时支持商业漏扫报告解析，将漏洞纳入统一管理。通过一站式的管理方案，降低安全管理风险，构建持续改进的安全运营闭环。

![漏洞管理](assets/2.png)

<p align="center">
  <img src="assets/18.png" alt="漏洞发现" width="49%" />
  <img src="assets/19.png" alt="漏洞跟踪" width="49%" />
</p>

### 3. 资产测绘

资产测绘用于对网络空间中的资产进行全面梳理、识别和定位，发现和管理企业或组织在网络中的各类资产（硬件设备、软件系统、服务等），从而迅速定位网络中的各类资产，收敛暴露资产，减少攻击面。

**主机测绘**：帮助用户发现目标网络环境中未被发现和掌握的主机资产。系统通过多线程并发方式对目标主机端口进行扫描和指纹识别，扫描目标支持 IP 范围和子网格式，内置常见扫描端口模板，并提供线程设置。

<p align="center">
  <img src="assets/23.png" alt="主机资产测绘" width="49%" />
  <img src="assets/24.png" alt="主机测绘结果" width="49%" />
</p>

**应用测绘**：高度集成的网络空间资产测绘能力，除端口扫描、目录探测、子域爆破和指纹识别外，还融合了以下关键技术与应用场景。

- **多层次扫描技术**
  - **端口扫描**：基于应用资产，识别开放的其他端口及服务类型（如 HTTP、SSH、数据库服务等）。
  - **子域爆破**：通过字典枚举或搜索引擎发现隐藏子域，结合 DNS 解析获取关联 IP。
  - **目录探测**：基于工具爆破敏感路径，识别未公开的 API、管理后台或配置文件泄露。
- **智能指纹识别**：通过 Banner 抓取、SSL 证书解析、协议特征匹配识别服务类型及版本。
- **自动化与关联分析**：自动聚合子域名、端口、服务等数据，与用户现有资产进行关联分析，识别新资产和失效资产，并提供不同视角查看资产情况和资产认领。

<p align="center">
  <img src="assets/25.png" alt="应用资产测绘" width="49%" />
  <img src="assets/26.png" alt="应用测绘结果" width="49%" />
  <img src="assets/3.png" alt="应用测绘配置" width="49%" />
  <img src="assets/4.png" alt="应用测绘任务" width="49%" />
  <img src="assets/5.png" alt="应用测绘详情" width="49%" />
</p>

### 4. 配置核查

提供主机批量化远程配置核查功能，确保系统配置符合安全标准。该功能采用无代理架构，直接通过 SSH 协议与目标系统建立连接，无需在目标系统上安装任何代理软件，减少了对目标系统的侵入性，降低了安全风险。其核心在于通过远程扫描、分析、评估、测试及自动加固技术，实现对服务器操作系统全面安全配置核查和加固。系统预置等保 2.0 要求检查项，支持 Windows/Linux 操作系统核查，支持自定义检查基线，可根据检查要求灵活定制。

![配置核查](assets/6.png)

<p align="center">
  <img src="assets/20.png" alt="配置核查" width="49%" />
  <img src="assets/21.png" alt="核查基线" width="49%" />
  <img src="assets/22.png" alt="核查结果" width="49%" />
</p>

### 5. 漏洞检测

漏洞检测功能基于 nuclei 实现，通过预定义的或自定义的 YAML 模板（Nuclei Templates）对目标进行自动化扫描，支持多种协议（HTTP、DNS、TCP 等），能够高效精准地识别潜在安全威胁，并提供可视化的 POC 模板管理界面，方便快速导入收集的 POC 模板。检测目标支持按 IP 范围、子网、URL 形式。

> 本仓库根目录提供了常用 POC 模板包 `poc模板0331.zip`，可在「POC 模板管理」中导入使用。

![漏洞检测](assets/7.png)

<p align="center">
  <img src="assets/27.png" alt="漏洞检测" width="49%" />
  <img src="assets/28.png" alt="POC 模板管理" width="49%" />
</p>

### 6. 弱口令检测

弱口令检测用于检测系统中可能存在的弱密码风险，支持 46 种协议，包括 SSH、RDP、POP3、FTP、Telnet、MySQL 等，可以帮助用户快速发现系统中的弱密码账号，提前发现安全隐患。系统内置高频使用爆破的字典库，同时支持用户自定义上传和管理字典文件。

![弱口令检测](assets/8.png)

<p align="center">
  <img src="assets/29.png" alt="弱口令检测" width="49%" />
  <img src="assets/30.png" alt="弱口令检测结果" width="49%" />
</p>

### 7. 主机运维

提供在线终端 SSH 服务，支持快捷命令、自定义快捷键和主题风格，旨在为用户打造一个高度个性化且高效便捷的远程操作环境。用户无需繁琐配置，即可快速接入远程服务器，执行各类复杂任务（需先录入主机资产和账号）。

<p align="center">
  <img src="assets/9.png" alt="主机运维" width="49%" />
  <img src="assets/31.png" alt="在线终端" width="49%" />
</p>

### 8. 批量执行

支持批量执行主机命令、多主机文件分发等功能，可极大提升运维人员的工作效率，减少重复性劳动。通过预设的命令模板或自定义脚本，运维人员能够一次性在多台主机上执行相同的操作，无论是系统更新、配置修改还是日志收集，都能迅速完成，确保各主机环境的一致性。

多主机文件分发功能使软件安装包、配置文件等能够快速且准确地部署到指定主机，避免手动逐台传输的繁琐与易错。此外，系统还支持任务调度与自动化执行，可根据预设时间或触发条件自动执行命令与文件分发任务（计划任务），实现运维工作的智能化与无人值守化。

![批量执行](assets/10.png)

<p align="center">
  <img src="assets/32.png" alt="批量执行" width="49%" />
  <img src="assets/33.png" alt="文件分发" width="49%" />
</p>

### 9. 报告管理

支持创建报告任务，将资产、漏洞、配置核查等检测数据汇总输出为标准化报告，并提供漏洞数量分析、漏洞修复情况分析、漏洞趋势分析等统计视图，为安全运营与汇报提供数据支撑。

### 10. 设备巡检

支持设备巡检记录的填报与更新，巡检结果留痕可追溯，便于形成日常安全运维台账。

### 11. 日志审计

记录用户操作日志，提供审计功能，是保障系统安全与合规性的重要举措。通过详细记录用户的每一次操作行为（操作时间、操作类型、操作对象、操作结果等关键信息），系统管理员能够全面掌握用户的活动轨迹。这些日志数据不仅有助于在出现问题时快速定位故障源头，还能为安全事件的调查提供有力证据：当系统出现异常数据修改时，管理员可以回溯日志，找出具体是哪个用户在何时进行了相关操作，从而判断是误操作还是恶意行为。

同时，审计功能也能对用户行为起到一定的约束作用——用户知晓自己的操作会被记录，就会更加谨慎地操作系统，减少违规操作的可能性。此外，定期对操作日志进行分析，还能发现系统使用过程中的潜在风险和优化点，进一步提升系统的安全性和稳定性。

![日志审计](assets/11.png)

![运维审计](assets/34.png)

## 快速开始

安全运维工具箱提供 Windows 客户端、Linux 部署包和 Docker 镜像三种使用方式，可按实际环境选择。

### Windows 部署

开箱即用，系统运行依赖环境已全部集成在程序包内，并提供桌面可视化管理界面。

#### 环境要求

- 操作系统：Windows 7/10/Server 2012+
- Npcap 1.80+：主机和应用资产测绘依赖，请在使用资产测绘功能前先安装 Npcap（本仓库根目录已提供 `npcap-1.80.exe`，也可从 <https://npcap.com/#download> 下载）
- 系统使用了 MySQL 8，需要确保安装了 Microsoft Visual C++ 2019 Redistributable Package 以上版本（本仓库根目录已提供 `VC_redist.x64.exe`）

#### 程序包目录结构

| 目录 | 说明 |
| --- | --- |
| `bin` | 启动程序所在目录 |
| `data` | 系统初始化后数据库文件存放目录 |
| `env` | 系统运行依赖的环境 |
| `etc` | 系统配置目录 |
| `lib` | 系统依赖包目录 |
| `logs` | 系统运行日志文件目录 |
| `resources` | 系统使用的资源目录 |

#### 安装步骤

**第一步：下载最新版本**

<https://github.com/nbyiansec/sskit/releases>

**第二步：运行程序**

解压后，在 `bin` 目录下找到「安全运维工具箱.exe」文件，双击打开系统管理界面，管理界面提供启动、停止、重启、卸载操作。

> ⚠️ 解压目录中不能包含空格、中文字符、其他特殊字符，否则运行失败；如安装有杀毒软件，建议将解压目录加白名单。

- **启动**：启动系统，当窗口标题显示「运行中」表示启动成功。第一次启动较慢，系统需要初始化环境和数据。
- **停止**：停止系统，系统将安全停止所有服务进程，等待服务完全停止后方可进行其他操作。
- **重启**：重启系统。
- **卸载**：卸载系统数据，系统将完全移除所有运行数据，卸载操作不可逆，操作前请确保重要数据已备份。
- **查看日志**：点击右下角查看日志，日志区域会显示启动过程信息。

![系统管理界面](assets/12.png)

**第三步：访问系统**

打开浏览器输入：<https://127.0.0.1:57701/kit/index.html>

默认账号：`admin / Admin@1290`，首次登录后请及时修改默认密码。

### Linux 部署

#### 环境要求

- 操作系统：Ubuntu 22.04.5 LTS 服务器版

#### 安装依赖组件

**1. 安装 nmap**

```bash
sudo apt install nmap
```

**2. 安装 hydra**

```bash
sudo apt install hydra
```

**3. 安装 python3 及依赖**

检查是否已安装 python3，推荐 3.8.10 及以上版本，Ubuntu 22.04.5 LTS 操作系统默认已安装。在系统安装文件目录下找到 `requirements.txt` 文件，使用以下命令安装依赖：

```bash
sudo pip3 install -r requirements.txt
```

**4. 安装 MySQL 8 以上版本**

<https://dev.mysql.com/downloads/mysql/>

**5. 安装 Redis**

<https://redis.io/downloads/>

**6. 安装 Nginx**

<https://nginx.org/>

#### 初始化数据库

创建用户和数据库，在安装目录下找到 `resources/sql/sskit_kit.sql` 文件导入 MySQL 数据库中。

#### 修改配置文件

**1. 修改系统配置文件 `etc/application.yaml`**

按照实际情况调整 MySQL、Redis、hydra、nmap 参数值。

```yaml
server:
  sskit-port: 57702 #api端口号
db:
  url: jdbc:mysql://127.0.0.1:57709/sskit_kit?useUnicode=true&characterEncoding=UTF-8&zeroDateTimeBehavior=convertToNull&allowPublicKeyRetrieval=true&useSSL=false&serverTimezone=Asia/Shanghai&autoReconnect=true
  username: 数据库用户名
  password: 数据库密码
redis-config:
    host: 127.0.0.1
    port: 56379
    password: redis密码
tool:
  python: /usr/bin/python3
  hydra: /usr/bin/hydra
  nmap: /usr/bin/nmap
```

**2. 修改 Nginx 配置**

根据 Nginx 配置文件所在目录，按下面模板进行调整。

```nginx
server {
    listen       57701 ssl;
    server_name  localhost;
    ssl_certificate  ../../../resources/certificate/sskit.crt;
    ssl_certificate_key ../../../resources/certificate/sskit.key;
    error_page 497 https://$host:57701/kit/index.html;
    access_log  ../../logs/sskit.access.log  main;
    location ^~ /kit/ {
        alias ../../resources/ui/kit/;#前端程序
        index index.html;
    }
    location ^~ /sskit/api {
      proxy_set_header Host $host;
      proxy_set_header X-Real-IP  $remote_addr;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header X-Forwarded-Proto $scheme;
      proxy_pass http://127.0.0.1:57702/sskit/api;#后端接口，此处端口需要与etc/application.yaml文件中server.sskit-port保持一致
    }
    location ^~ /sskit/keep-alive {
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_read_timeout 3600s;
        proxy_send_timeout 3600s;
      proxy_pass http://127.0.0.1:57702/sskit/keep-alive;#后端接口，此处端口需要与etc/application.yaml文件中server.sskit-port保持一致
    }
}
```

#### 启动系统

在 `bin` 目录中，以管理员权限运行启动脚本 `startup.sh`：

```bash
sudo ./startup.sh
```

可查看 `logs/sskit/app.log` 日志文件，跟踪启动状态：

```
2025-09-04 10:56:25.756 -  INFO [] [main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 57702 (http) with context path ''
.....
2025-09-04 10:56:25.820 -  INFO [] [main] c.y.sskit.launch.LaunchApplication       : Started LaunchApplication in 17.954 seconds (JVM running for 18.692)
```

#### 访问系统

打开浏览器输入：<https://localhost:57701/kit/index.html>

默认账号：`admin / Admin@1290`，首次登录后请及时修改默认密码。

### Docker 部署

通过 Docker 可快速部署 SSKit，无需手动安装 MySQL、Redis、Nginx 等依赖，应用已内置在镜像中。

#### 环境要求

- Docker Engine 20.10+
- Docker Compose 2.0+
- 内存 4GB+，磁盘 20GB+

#### 部署步骤

**第一步：获取部署文件**

```bash
git clone https://github.com/nbyiansec/sskit.git
cd sskit/docker
```

**第二步：配置环境变量**

```bash
cp .env.example .env
vi .env
```

按需修改 `.env` 中的镜像版本 `TAG`、对外端口 `NGINX_PORT`、数据库密码等配置，生产环境请务必修改默认密码。

**第三步：拉取镜像并启动**

```bash
docker compose up -d
```

**第四步：访问系统**

- 地址：<https://localhost:57701/kit/index.html>
- 默认账号：`admin / Admin@1290`

> 首次访问浏览器会提示证书不受信任（自签名证书），点击继续访问即可。首次登录后请修改默认密码。

#### 使用外部数据库

如果已有 MySQL 和 Redis 服务，修改 `.env` 中 `MYSQL_HOST` 和 `REDIS_HOST` 为外部地址，然后使用简化版部署：

```bash
docker compose -f docker-compose.simple.yml up -d
```

外部数据库要求：MySQL 8.0+（需开启 `lower_case_table_names=1`）、Redis 6.0+。

#### 常用命令

```bash
docker compose ps            # 查看状态
docker compose logs -f app   # 查看日志
docker compose down          # 停止服务
docker compose down -v       # 停止并清除数据（慎用）
```

## 常见问题

**1. 初始化失败**

若安全运维工具箱第一次运行时提示初始化失败，请检查安装路径中是否包含中文或特殊符号（如 `-`），以及是否安装 Microsoft Visual C++ 2019 Redistributable Package。

**2. 升级失败**

为避免升级失败，建议采取以下措施：将工具箱安装至除 C 盘以外的目录，防止因权限问题影响升级操作；升级前先将安全运维工具箱目录加白名单，避免被误杀。

**3. 配置核查、弱口令检测、漏洞检测、资产测绘失败**

可能原因是杀毒软件误杀，将依赖组件清除，导致扫描失败。请检查杀毒软件隔离区或日志，恢复被清除的工具，并将安全运维工具箱文件添加至信任列表。

**4. 漏洞检测执行失败提示「执行命令失败」**

请检查 POC 模板是否完成初始化，确保模板配置正确后重新执行任务。

## 更新日志

完整版本历史请查看 [Releases](https://github.com/nbyiansec/sskit/releases)。

**v1.0.6**

新增

- 新增「互联网搜索」任务类型，支持「查企业」「查 IP/域名」，接入鹰图、夸克引擎
- 查企业支持结果降噪（默认开启），自动过滤无效备案与噪音域名；支持一次输入多个目标自动拆分，搜索记录可批量导出
- 网站扫描新增鹰图、Quake 引擎，原仅支持本地引擎，现可选择鹰图、Quake 进行多引擎测绘
- 「网络空间」更名为「项目空间」，顶栏改为「当前项目空间」

其他改进

- 配置核查基线脚本判定修复，减少误报；支持导入单机 xml 结果，汇总报告新增合规项 / 不合规项统计
- 修复服务项目切换后弹窗不关闭、页面不刷新

> 使用互联网搜索前，请在「系统设置 → 系统参数」中配置鹰图 / Quake API Key。

**v1.0.5**

- 新增离线配置核查与加固功能，支持在离线环境下进行配置核查和加固
- 离线客户端兼容 Windows Server 2008 R2 及以上、主流 Linux 操作系统（包括 ARM 架构，以及统信 UOS、银河麒麟等国产化操作系统）

## 反馈与支持

SSKit 社区版免费开放，旨在让更多安全运维团队用上这套工具，同时通过大家的真实使用反馈持续打磨产品。使用过程中遇到问题或有新的需求，欢迎自主提交，我们会不定期跟进处理。

- [提交 Bug](https://github.com/nbyiansec/sskit/issues/new)：请附上版本号、操作系统、问题现象、复现步骤，以及错误截图或日志，便于快速定位
- [提交需求](https://github.com/nbyiansec/sskit/issues/new)：请说明使用场景、期望效果和优先级，便于我们评估与排期

> 本软件为**免费使用（非开源）**软件，不接收代码贡献。

## 致谢

特别感谢以下开源项目，你们的无私分享为软件开发提供了坚实基础。

- [orion-visor](https://github.com/dromara/orion-visor) — 主机运维与在线终端
- [EHole](https://github.com/EdgeSecurityTeam/EHole) — 指纹识别
- [dirsearch](https://github.com/maurosoria/dirsearch) — 目录探测
- [nmap](https://github.com/nmap/nmap) — 端口扫描
- [OneForAll](https://github.com/shmilylty/OneForAll) — 子域收集

## 授权许可

本软件为免费使用（非开源）软件，采用自定义许可协议，完整条款见 [LICENSE](LICENSE)。

1. 未经商业授权，禁止将本软件用于任何盈利活动（包括但不限于商业培训、SaaS 服务、嵌入式系统销售等）。
2. 禁止移除或修改软件中的 logo 标识和版权申明。

如需商业授权或功能定制，请通过 [Issues](https://github.com/nbyiansec/sskit/issues) 联系我们。

## 免责声明

本工具仅能在取得足够合法授权的企业安全建设中使用，在使用本工具过程中，您应确保自己所有行为符合当地的法律法规。禁止将软件用于违法用途，如您在使用本工具的过程中存在任何非法行为，您将自行承担所有后果，本工具所有开发者和所有贡献者不承担任何法律及连带责任。使用本软件产生的任何直接/间接损失（如数据丢失、业务中断等），开发者概不负责。除非您已充分阅读、完全理解并接受本协议所有条款，否则，请您不要安装并使用本工具。您的使用行为或者您以其他任何明示或者默示方式表示接受本协议的，即视为您已阅读并同意本协议的约束。

## 关于我们

壹安科技是国内首批聚焦网络安全服务的专业技术公司，公司专注网络和数据安全技术研究与应用，为企业提供技术咨询、运维管理、应急保障等一站式专业安全服务，打通网络安全管理最后一公里，构建完整安全防护体系，实现信息系统风险全生命周期管理。

公司总结多年一线安全服务经验与技术研究成果，针对性研发出安全运维工具箱等技术工具与平台，为广大网络安全从业人员提供专业技术支持。

## 联系我们

使用过程中有任何问题，或者对项目有什么想法或者建议，可以提交 Issues，将不定期进行回复和解决问题。如有合作/功能定制需求请加微信，备注：合作。

![联系微信](assets/35.png)
