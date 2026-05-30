# MissingPoC-Hub

<p align="center">
  <img src="https://img.shields.io/badge/PoC-Missing%20PoC%20Supplement-orange" />
  <img src="https://img.shields.io/badge/Writeups-Reproduction%20Notes-blue" />
  <img src="https://img.shields.io/badge/Use-Authorized%20Only-red" />
  <img src="https://img.shields.io/badge/Security-Lab%20Only-green" />
</p>

## 项目简介

**MissingPoC-Hub** 是一个专注于补充“缺失 PoC 漏洞”的安全研究项目。

@makabaga123 @W5M1n9

在复现 Vulhub、CNVD、公开漏洞复现平台、靶场环境或安全文章中的漏洞时，经常会遇到一种情况：漏洞环境、漏洞描述或漏洞编号已经存在，但缺少清晰可用的 PoC，或者现有复现资料不够完整。

本项目主要用于收集这类缺少 PoC 的漏洞，并为每个漏洞补充：

* PoC 编写思路
* 最小化 PoC 脚本
* 漏洞复现步骤
* 复现截图

本项目不提供漏洞环境，不维护 Docker 环境，也不重复搬运靶场文件。如果漏洞来源于 Vulhub、CNVD、其他公开平台或文章环境，请自行前往原平台搭建对应环境。本仓库只关注 PoC 编写和复现过程记录。

## 项目定位

本项目不是漏洞利用武器库，也不是批量扫描工具集合。

本项目的核心目标是：

1. 记录没有公开 PoC 或 PoC 不完整的漏洞。
2. 编写最小化、可读、可复现的 PoC 脚本。
3. 整理漏洞复现步骤，方便学习和回顾。
4. 分析 PoC 的构造思路，而不是只堆脚本。
5. 帮助安全学习者理解漏洞触发过程和 PoC 编写方法。

## 适用场景

本项目适用于：

* CVE 漏洞复现学习
* CNVD 漏洞复现学习
* Vulhub 漏洞 PoC 补充
* Web 安全漏洞分析
* 组件漏洞复现
* PoC 编写练习
* 安全研究笔记沉淀
* 个人安全项目展示

本项目不适用于：

* 未授权攻击
* 公网批量扫描
* 数据窃取
* 反弹 Shell
* 后门植入
* 权限维持
* 横向移动
* 恶意利用第三方系统

## 仓库结构

```text
.
├── Vulhub/
│   └── CVE-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── writeups.md
│       └── screenshots/
│
├── CNVD/
│   └── CNVD-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── writeups.md
│       └── screenshots/
│
├── Other-Platforms/
│   └── CVE-YYYY-NNNN/
│       ├── README.md
│       ├── poc.py
│       ├── writeups.md
│       └── screenshots/
│
├── DISCLAIMER.md
├── CONTRIBUTING.md
├── SECURITY.md
├── LICENSE
└── README.md
```

## 目录说明

### `Vulhub/`

用于存放来自 Vulhub 平台，但原环境中缺少 PoC 或复现资料不完整的漏洞。

示例：

```text
Vulhub/
└── CVE-202X-XXXX/
    ├── README.md
    ├── poc.py
    ├── writeups.md
    └── screenshots/
```

### `CNVD/`

用于存放 CNVD 相关漏洞的 PoC 和复现 Writeup。

如果漏洞同时存在 CVE 编号和 CNVD 编号，可以根据主要来源选择目录命名方式。推荐优先使用 CNVD 编号，例如：

```text
CNVD/
└── CNVD-202X-XXXX/
    ├── README.md
    ├── poc.py
    ├── writeups.md
    └── screenshots/
```

### `Other-Platforms/`

用于存放其他平台、文章环境、公开靶场或自行复现过程中遇到的缺失 PoC 漏洞。

如果漏洞有 CVE 编号，建议使用 CVE 编号命名：

```text
Other-Platforms/
└── CVE-202X-XXXX/
    ├── README.md
    ├── poc.py
    ├── writeups.md
    └── screenshots/
```

如果漏洞没有明确 CVE 编号，可以使用漏洞名称或平台编号命名：

```text
Other-Platforms/
└── product-name-unauth-file-read/
    ├── README.md
    ├── poc.py
    ├── writeups.md
    └── screenshots/
```

## 单个漏洞目录规范

每个漏洞目录固定包含四个核心部分：

```text
CVE-YYYY-NNNN/
├── README.md
├── poc.py
├── writeups.md
└── screenshots/
```

### `README.md`

用于记录 **PoC 编写思路**。

建议包含：

* 漏洞基本信息
* 漏洞入口分析
* 关键参数说明
* Payload 构造思路
* PoC 编写过程
* 漏洞判断逻辑
* 修复建议
* 参考链接

`README.md` 重点写“这个 PoC 是怎么想出来、怎么写出来的”。

### `poc.py`

用于存放 **最小化 PoC 脚本**。

PoC 应该尽量保持：

* 简洁
* 可读
* 可复现
* 无害化
* 只用于验证漏洞是否存在

不建议默认包含：

* 反弹 Shell
* 批量扫描
* 后门植入
* 凭据窃取
* 破坏性命令
* 持久化逻辑

### `writeups.md`

用于记录 **完整复现步骤**。

建议包含：

* 环境来源
* 环境启动方式
* 目标访问地址
* 漏洞触发流程
* PoC 运行方式
* 复现结果
* 遇到的问题
* 复现总结

`writeups.md` 重点写“别人如何一步一步复现这个漏洞”。

### `screenshots/`

用于存放 **复现过程截图**。

建议截图包括：

* 靶场环境启动成功截图
* 漏洞页面截图
* 请求包截图
* PoC 运行结果截图
* 漏洞触发成功截图

## 漏洞索引

| 平台              | 漏洞编号           | 漏洞类型 | 影响组件            | PoC | Writeup | 状态  |
| --------------- | -------------- | ---- | --------------- | --- | ------- | --- |
| Vulhub          | CVE-YYYY-NNNN  | RCE  | Example Product | ✅   | ✅       | 已完成 |
| CNVD            | CNVD-YYYY-NNNN | 文件读取 | Example Product | ✅   | ✅       | 已完成 |
| Other-Platforms | CVE-YYYY-NNNN  | SSRF | Example Product | 🚧  | 🚧      | 编写中 |

状态说明：

* ✅ 已完成
* 🚧 编写中
* ❌ 暂未完成

## PoC 使用方式

进入对应漏洞目录：

```bash
cd Vulhub/CVE-YYYY-NNNN
```

运行 PoC：

```bash
python3 poc.py --url http://127.0.0.1:8080
```

预期输出示例：

```text
[+] Target: http://127.0.0.1:8080
[+] Checking vulnerability...
[+] Target appears vulnerable
```

注意：请只在本地靶场、授权测试环境或自己拥有的系统中运行 PoC。

## PoC 编写原则

本项目中的 PoC 应遵循以下原则：

1. PoC 只用于验证漏洞是否存在。
2. 默认面向本地靶场或授权测试环境。
3. 默认目标建议为 `127.0.0.1`、`localhost` 或内网测试地址。
4. 不提供公网批量扫描功能。
5. 不默认提供反弹 Shell。
6. 不包含后门、木马、持久化或凭据窃取逻辑。
7. Payload 应尽量无害化。
8. 代码应清晰、可读、可复现。
9. 每个关键参数和 Payload 都应在 `README.md` 中说明。
10. 每个漏洞都应在 `writeups.md` 中提供完整复现步骤。

## 推荐 PoC 输出格式

建议 PoC 使用清晰的命令行参数：

```bash
python3 poc.py --url http://127.0.0.1:8080
```

建议输出格式：

```text
[+] Target: http://127.0.0.1:8080
[+] Sending payload...
[+] Target appears vulnerable
```

如果验证失败：

```text
[-] Target does not appear vulnerable
```

## 单个漏洞 README.md 推荐结构

```markdown
# CVE-YYYY-NNNN - 漏洞名称

## 1. 漏洞信息

- 漏洞编号：
- 漏洞类型：
- 影响组件：
- 影响版本：
- 环境来源：
- PoC 语言：

## 2. 漏洞简介

简要说明漏洞背景、影响范围和触发条件。

## 3. PoC 编写思路

说明这个 PoC 是如何推导出来的，例如：

- 漏洞入口在哪里
- 哪些参数可控
- 关键请求是什么
- Payload 为什么这样构造
- 如何判断漏洞触发成功
- PoC 中每一步对应的漏洞逻辑是什么

## 4. 关键代码说明

解释 `poc.py` 中的关键代码逻辑。

## 5. 漏洞原理分析

说明漏洞产生的原因，例如：

- 输入校验不足
- 权限控制缺失
- 文件路径过滤不严
- 模板注入
- 反序列化风险
- 命令拼接导致 RCE
- SSRF 目标限制不严

## 6. 修复建议

给出修复方式，例如：

- 升级到安全版本
- 增加权限校验
- 限制危险函数
- 过滤用户输入
- 禁用不必要功能
- 增加网络访问控制

## 7. 参考链接

- 官方公告：
- CVE / CNVD：
- 原始环境：
- 补丁链接：
- 参考文章：
```

## 单个漏洞 writeups.md 推荐结构

````markdown
# CVE-YYYY-NNNN - 复现步骤

## 1. 环境来源

说明漏洞环境来自哪里，例如：

- Vulhub
- CNVD 公开漏洞环境
- 其他公开靶场
- 安全文章环境
- 自行搭建测试环境

本仓库不提供环境文件，请参考原始平台完成环境搭建。

## 2. 环境启动

记录环境启动方式，例如：

```bash
docker compose up -d
````

## 3. 访问目标

记录目标地址：

```text
http://127.0.0.1:8080
```

## 4. 漏洞复现

记录手工复现过程，包括请求路径、参数、Payload 和响应结果。

## 5. PoC 验证

运行 PoC：

```bash
python3 poc.py --url http://127.0.0.1:8080
```

## 6. 复现结果

说明漏洞是否成功触发，并附上截图。

## 7. 问题记录

记录复现过程中遇到的问题，例如：

* 环境启动失败
* 端口冲突
* 依赖问题
* Payload 无回显
* 版本不匹配

## 8. 复现总结

总结漏洞触发条件、验证方式和复现注意事项。

```

## 贡献指南

欢迎提交新的缺失 PoC、复现 Writeup 或对已有内容进行完善。

提交内容建议包括：

- 明确的平台来源
- 明确的漏洞编号或漏洞名称
- `README.md`：PoC 编写思路
- `poc.py`：最小化 PoC 脚本
- `writeups.md`：完整复现步骤
- `screenshots/`：复现截图
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
- [ ] 整理 CNVD 相关漏洞的 PoC 和复现步骤
- [ ] 补充其他平台中的缺失 PoC 案例
- [ ] 建立统一的单漏洞目录规范
- [ ] 建立统一的 PoC 编写规范
- [ ] 增加漏洞类型索引
- [ ] 增加 PoC from Scratch 系列记录
- [ ] 增加 Web 安全、云原生安全、组件漏洞分类

## 免责声明

本项目仅用于网络安全学习、漏洞复现研究和授权测试。

请勿将本项目中的代码、文档或技术细节用于任何未授权测试或非法攻击行为。使用者应自行确保所有测试行为符合当地法律法规，并已经获得目标系统所有者的明确授权。

项目作者不对任何滥用行为、非法行为或由此造成的损失承担责任。

## License

本项目采用 Apache License 2.0 开源许可证，详情请查看 [LICENSE](./LICENSE)。
```
