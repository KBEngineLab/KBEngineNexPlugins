# KBEngineNex 插件源

KBEngineNex 官方插件索引仓库，`plugins-source.json` 定义所有可用插件及其版本。

## 源结构

```jsonc
{
  "name": "KBEngineNex Plugins",   // 源名称
  "version": "0.1.0",              // 源自身版本
  "description": "...",            // 源描述
  "maintainer": "KBEngineLab",     // 维护者
  "plugins": [
    {
      "id": "DbStress",            // 唯一标识，对应仓库名后缀
      "name": "DbStress",          // 插件显示名
      "description": "...",        // 插件简介
      "author": "KBEngineLab",     // 作者
      "category": "tool",          // 分类：tool / gameplay / ...
      "tags": [...],               // 搜索关键词
      "github": "https://...",     // GitHub 仓库地址
      "gitee": "https://...",      // Gitee 仓库地址
      "versions": [
        {
          "version": "0.1.0",      // 版本号
          "github": "https://...", // GitHub zip 下载链接
          "gitee": "https://..."   // Gitee zip 下载链接
        }
      ]
    }
  ]
}
```

### 字段说明

**插件级字段**（跨版本不变）：

| 字段 | 类型 | 说明 |
|------|------|------|
| `id` | string | 唯一标识，不可重复 |
| `name` | string | 展示名称 |
| `description` | string | 一句话简介 |
| `author` | string | 作者 / 组织 |
| `category` | string | 分类 |
| `tags` | string[] | 搜索标签 |
| `github` | string | GitHub 仓库首页 |
| `gitee` | string | Gitee 仓库首页 |
| `versions` | array | 版本列表 |

**版本级字段**：

| 字段 | 类型 | 说明 |
|------|------|------|
| `version` | string | 语义化版本号 |
| `github` | string | 该版本在 GitHub 的 zip 下载直链 |
| `gitee` | string | 该版本在 Gitee 的 zip 下载直链 |

> zip 直链格式：`{repo}/releases/download/v{version}/{Name}-{version}.zip`

## 贡献插件

### 1. 准备

你的插件需包含 `plugin.json` 并已完成版本发布（GitHub Release 含 zip 附件）。

### 2. 添加条目

Fork 本仓库，在 `plugins-source.json` 的 `plugins` 数组末尾追加：

```json
{
  "id": "MyPlugin",
  "name": "MyPlugin",
  "description": "插件简介",
  "author": "你的名字",
  "category": "玩法",
  "tags": ["标签1", "标签2"],
  "github": "https://github.com/xxx/KBEngineNex-Plugin-MyPlugin",
  "gitee": "https://gitee.com/xxx/kbenginenex-plugin-myplugin",
  "versions": [
    {
      "version": "0.1.0",
      "github": "https://github.com/xxx/KBEngineNex-Plugin-MyPlugin/releases/download/v0.1.0/MyPlugin-0.1.0.zip",
      "gitee": "https://gitee.com/xxx/kbenginenex-plugin-myplugin/releases/download/v0.1.0/MyPlugin-0.1.0.zip"
    }
  ]
}
```

### 3. 提交

确保 JSON 格式合法后提 PR，审核通过即收录。

### 4. 更新版本

发布新版本后，在对应插件的 `versions` 数组中追加新版本条目即可，旧版本保留不删。
