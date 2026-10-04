# LiG VS Code Preview

这是一套供人工试用的生成产物，未替换正式 LiG 主题。四套 variant 来自同一个 OKLCH core 与 shared styles。


## 安装（MacBook 的 VS Code）

```sh
curl -fL https://github.com/0froq/vscode-theme-LiG-preview/releases/download/preview-2026-10-04.1/theme-lig-preview-0.0.1.vsix -o /tmp/theme-lig-preview.vsix
code --install-extension /tmp/theme-lig-preview.vsix
```

若终端没有 `code`，在 VS Code 命令面板使用 `Extensions: Install from VSIX...` 选择下载文件。
随后 `Preferences: Color Theme` 选择 LiG Preview Dark / Light / Dark Soft / Light Soft。

Extension ID 是 `froQ.theme-lig-preview`，与现有 `froQ.theme-lig` 独立。最低 VS Code 版本沿用 1.107.0。

## 覆盖与测试重点

- 基础编辑界面、诊断、选区、terminal 16 色。
- 191 个 Workbench keys、TextMate 与 semantic tokens；是否收到 semantic tokens 取决于语言扩展。
- 对比 TS/Python 中的 variable / keyword、类型定义 / 引用、函数定义 / 调用、字符串 / 注释。
- 试用四套主题、选区/搜索/诊断。比较 semantic highlighting 开启与关闭时的分类。
- 当前 dark 与 dark-soft 的 token 完全相同；保留独立名称，后续再校准。
- 字体与最终视觉效果由用户在实际编辑器手动确认；构建检查不等于视觉验收。

## 单一事实源

请在 [LiG source snapshot](https://github.com/0froq/lig/tree/preview-ports-2026-10-04.1) 修改 design/core/compiler；不要手改这里的 generated 文件。

Design version: 0.2.0
Compiler version: 0.1.0
Input SHA-256: `677c3003409f405a885b9cad88783ae302a172a76918871b83024a10ddb8e813`

`lig-build.json` 包含该 repo 的每个文件 checksum。Preview 是静态 native 产物，安装时无需 Node，也不会从网络加载 tokens。
