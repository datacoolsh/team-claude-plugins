---
description: 检查并安装 uv，然后在当前项目初始化 .venv 虚拟环境
allowed-tools: Bash
---

请按以下步骤执行，每步用 Bash 工具运行命令：

## 第一步：检查 uv 是否已安装

```bash
uv --version
```

- 如果命令成功返回版本号，说明 uv 已安装，跳到第三步。
- 如果命令失败（找不到命令），继续第二步。

## 第二步：安装 uv

根据当前操作系统选择安装方式：

**Windows（PowerShell）：**
```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS / Linux：**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

安装完成后，刷新 PATH 并再次验证：
```bash
uv --version
```

## 第三步：配置 uv（设置国内镜像加速，可选）

检查是否有 UV_INDEX_URL 环境变量，如果没有设置，输出提示用户可按需配置：
- 国内用户推荐设置：`UV_INDEX_URL=https://pypi.tuna.tsinghua.edu.cn/simple`

## 第四步：在当前目录初始化 .venv 虚拟环境

```bash
uv venv .venv
```

完成后输出虚拟环境路径和激活方式：
- Windows: `.venv\Scripts\activate`
- macOS/Linux: `source .venv/bin/activate`

最后汇总输出执行结果。
