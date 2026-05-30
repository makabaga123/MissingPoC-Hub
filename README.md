# MissingPoC-Hub

<p align="center">
  <img src="https://img.shields.io/badge/PoC-Missing%20PoC%20Supplement-orange" />
  <img src="https://img.shields.io/badge/Use-Authorized%20Only-red" />
  <img src="https://img.shields.io/badge/Writeups-Reproduction%20Notes-blue" />
  <img src="https://img.shields.io/badge/Security-Lab%20Only-green" />
</p>

## 项目简介

**MissingPoC-Hub** 是一个面向网络安全学习、漏洞复现和授权测试场景的 PoC 补全项目。

在复现 Vulhub、VulnHub、Pikachu、FOFA 公开漏洞环境、CTF 靶场或其他漏洞复现平台时，经常会遇到一些漏洞环境已经存在、漏洞描述也能找到，但缺少清晰可用 PoC 的情况。

本项目主要用于收集和补充这类“缺少 PoC 的漏洞”，为其编写最小化验证脚本，并附带对应的漏洞复现 Writeup。

本项目不会维护漏洞环境，也不会重复搭建靶场。如果某个漏洞来自 Vulhub、VulnHub 或其他平台，请优先参考原平台完成环境搭建。本仓库只关注：

* PoC 编写
* 漏洞复现步骤
* 触发过程分析
* 关键请求说明
* 漏洞原理理解
* 修复建议整理

## 项目定位

本项目不是漏洞利用武器库，也不是批量扫描工具集合。

本项目的目标是记录：

1. 某个漏洞为什么可以被触发。
2. PoC 应该如何从漏洞原理中推导出来。
3. 如何在本地靶场或授权环境中验证漏洞。
4. 如何用最小化、无害化的方式证明漏洞存在。
5. 如何把复现过程整理成清晰的 Writeup。

## 适用场景

本项目适用于：

* 网络安全学习
* CVE 漏洞复现
* Web 漏洞分析
* PoC 编写练习
* Vulhub 等靶场平台的 PoC 补充
* 安全研究笔记沉淀
* 面试或简历项目展示

本项目不适用于：

* 未授权攻击
* 公网批量扫描
* 数据窃取
* 反弹 Shell
* 后门植入
* 权限维持
* 横向移动
* 恶意利用第三方系统

## 项目特点

* **只放 PoC 和 Writeup**
  本仓库不维护漏洞环境。环境请参考 Vulhub、VulnHub 或其他原始靶场平台。

* **多平台收集**
  不局限于 Vulhub，也可以包含其他平台中缺少 PoC 或复现资料不完整的漏洞。

* **最小化验证**
  PoC 只用于证明漏洞是否存在，默认不包含攻击后利用逻辑。

* **复现过程清晰**
  每个漏洞尽量包含环境来源、复现步骤、关键请求、触发结果和截图说明。

* **重视 PoC 编写思路**
  不只是给出脚本，还会解释 PoC 是如何从漏洞描述、请求参数、源码逻辑或补丁分析中推导出来的。

* **安全边界明确**
  默认面向本地靶场和授权测试，不提供批量攻击、公网扫描或恶意 Payload。

## 仓库结构

```text
.
├── Vulhub/
│   └── CVE-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── requirements.txt
│       └── screenshots/
│
├── VulnHub/
│   └── CVE-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── requirements.txt
│       └── screenshots/
│
├── CTF-Platforms/
│   └── Vulnerability-ID/
│       ├── README.md
│       ├── poc.py
│       └── screenshots/
│
├── Other-Platforms/
│   └── CVE-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── requirements.txt
│       └── screenshots/
│
├── templates/
│   ├── writeup-template.md
│   └── poc-template.py
│
├── docs/
│   ├── poc-writing-guide.md
│   └── reproduction-notes.md
│
├── DISCLAIMER.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
└── README.md
```

## 目录说明

### `Vulhub/`

用于存放来自 Vulhub 平台，但原环境中缺少 PoC 或复现过程不够完整的漏洞。

示例：

```text
Vulhub/
└── CVE-202X-XXXX/
    ├── README.md
    ├── poc.py
    └── screenshots/
```

### `VulnHub/`

用于存放来自 VulnHub 或类似虚拟机靶场平台的漏洞复现 PoC 和 Writeup。

### `CTF-Platforms/`

用于存放来自 CTF、攻防演练靶场或练习平台中的漏洞验证脚本和复现笔记。

如果没有明确 CVE 编号，可以使用漏洞名称、题目名称或平台编号作为目录名。

### `Other-Platforms/`

用于存放其他公开漏洞复现平台、文章环境或自行搭建测试环境中发现的缺失 PoC 案例。

### `templates/`

用于存放统一的 Writeup 模板和 PoC 模板，方便后续保持项目格式一致。

### `docs/`

用于记录 PoC 编写规范、漏洞复现方法论、抓包分析思路等通用内容。

## 漏洞索引

| 平台              | 漏洞编号          | 漏洞类型          | 影响组件            | PoC | Writeup | 状态  |
| --------------- | ------------- | ------------- | --------------- | --- | ------- | --- |
| Vulhub          | CVE-YYYY-NNNN | RCE           | Example Product | ✅   | ✅       | 已完成 |
| Vulhub          | CVE-YYYY-NNNN | SSRF          | Example Product | 🚧  | 🚧      | 编写中 |
| Other-Platforms | CVE-YYYY-NNNN | SQL Injection | Example Product | ✅   | ✅       | 已完成 |

状态说明：

* ✅ 已完成
* 🚧 编写中
* ❌ 暂未完成

## 单个漏洞目录结构

每个漏洞目录建议保持如下结构：

```text
CVE-YYYY-NNNN/
├── README.md
├── poc.py
├── requirements.txt
└── screenshots/
```

如果 PoC 不需要额外依赖，可以不放 `requirements.txt`。

如果漏洞没有 CVE 编号，可以使用平台漏洞编号或漏洞名称，例如：

```text
SomePlatform/
└── unauth-file-read-example/
    ├── README.md
    ├── poc.py
    └── screenshots/
```

## 单个漏洞 Writeup 内容

每个漏洞的 `README.md` 建议包含以下内容：

1. 漏洞基本信息
2. 环境来源
3. 影响版本
4. 漏洞类型
5. 复现前提
6. 复现步骤
7. PoC 使用方式
8. PoC 编写思路
9. 关键请求分析
10. 触发结果截图
11. 漏洞原理分析
12. 修复建议
13. 参考链接

## PoC 使用方式

进入对应漏洞目录：

```bash
cd Vulhub/CVE-YYYY-NNNN
```

安装依赖：

```bash
pip install -r requirements.txt
```

运行 PoC：

```bash
python3 poc.py --url http://127.0.0.1:8080
```

预期输出示例：

```text
[+] Target appears vulnerable
```

注意：请只在本地靶场、授权测试环境或自己拥有的系统中运行 PoC。

## PoC 编写原则

本项目中的 PoC 应遵循以下原则：

1. PoC 应保持最小化，只用于验证漏洞是否存在。
2. 默认目标应为本地靶场地址，例如 `127.0.0.1`、`localhost` 或内网测试地址。
3. 不提供公网批量扫描功能。
4. 不默认包含反弹 Shell。
5. 不包含后门、木马、持久化或凭据窃取逻辑。
6. Payload 应尽量无害化。
7. 代码应清晰、可读、可复现。
8. 每个关键参数和请求都应在 Writeup 中解释清楚。
9. 尽量说明 PoC 的构造过程，而不是只给最终脚本。
10. 尽量附带修复建议和参考资料。

## 推荐 PoC 风格

PoC 应尽量使用清晰的命令行参数，例如：

```bash
python3 poc.py --url http://127.0.0.1:8080
```

建议输出格式：

```text
[+] Target: http://127.0.0.1:8080
[+] Checking vulnerability...
[+] Target appears vulnerable
```

不建议默认执行高风险命令或破坏性操作。

## Writeup 模板

````markdown
# CVE-YYYY-NNNN - 漏洞名称

## 1. 漏洞信息

- 漏洞编号：
- 漏洞类型：
- 影响组件：
- 影响版本：
- 环境来源：
- 复现平台：
- PoC 语言：

## 2. 漏洞简介

简要说明漏洞背景、漏洞影响和触发条件。

## 3. 环境来源

说明该漏洞环境来自哪个平台，例如：

- Vulhub
- VulnHub
- CTF 平台
- 公开文章环境
- 自行搭建测试环境

本仓库不提供环境文件，请参考原平台完成环境搭建。

## 4. 复现步骤

记录完整复现流程，包括访问路径、关键请求、参数构造和触发结果。

## 5. PoC 使用

说明 PoC 的运行方式和参数含义。

```bash
python3 poc.py --url http://127.0.0.1:8080
````

## 6. PoC 编写思路

说明 PoC 是如何写出来的，例如：

* 漏洞入口在哪里
* 关键参数是什么
* Payload 为什么这样构造
* 如何判断漏洞是否触发
* 哪些报错或响应可以作为漏洞存在的依据

## 7. 关键请求分析

可以放 HTTP 请求包、响应包或抓包截图。

## 8. 漏洞原理分析

说明漏洞产生的根本原因，例如：

* 输入校验不足
* 权限控制缺失
* 反序列化风险
* 模板注入
* 文件读取限制绕过
* 命令拼接导致 RCE
* SSRF 目标限制不严

## 9. 修复建议

给出修复方式，例如：

* 升级到安全版本
* 增加权限校验
* 限制危险函数
* 过滤用户输入
* 禁用不必要功能
* 增加网络访问控制

## 10. 参考链接

* 官方公告：
* NVD：
* 原始环境：
* 补丁链接：
* 参考文章：

```

## 贡献指南

欢迎提交新的缺失 PoC、复现 Writeup 或对已有内容进行改进。

提交内容建议包括：

- 明确的平台来源
- 明确的漏洞编号或漏洞名称
- 可运行的最小化 PoC
- 清晰的复现步骤
- PoC 编写思路
- 漏洞原理分析
- 修复建议
- 参考链接

不接受以下内容：

- 未授权攻击脚本
- 公网批量扫描工具
- 默认反弹 Shell 的脚本
- 后门、木马或持久化代码
- 凭据窃取相关代码
- 破坏性 Payload
- 无说明、无来源、无法复现的代码

## 后续计划

- [ ] 整理 Vulhub 中缺少 PoC 的漏洞
- [ ] 补充其他平台中的缺失 PoC 案例
- [ ] 建立统一 PoC 模板
- [ ] 建立统一 Writeup 模板
- [ ] 增加漏洞类型索引
- [ ] 增加 PoC from Scratch 系列笔记
- [ ] 增加补丁分析记录
- [ ] 增加抓包分析示例
- [ ] 增加 Web 安全、云原生安全、组件漏洞分类

## 免责声明

本项目仅用于网络安全学习、漏洞复现研究和授权测试。

请勿将本项目中的代码、文档或技术细节用于任何未授权测试或非法攻击行为。使用者应自行确保所有测试行为符合当地法律法规，并已经获得目标系统所有者的明确授权。

项目作者不对任何滥用行为、非法行为或由此造成的损失承担责任。

## License

本项目采用 Apache License 2.0 开源许可证，详情请查看 [LICENSE](./LICENSE)。
```
