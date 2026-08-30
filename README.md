# Sources

UIN Tool 插件源注册表。

## 说明

本仓库维护所有已知插件源的注册信息。UIN Tool 客户端启动时从此仓库拉取 `registry.json`，获取可用插件源列表。

## registry.json 字段说明

| 字段 | 类型 | 说明 |
|------|------|------|
| `sourceId` | string | 源唯一标识 |
| `name` | string | 源显示名称 |
| `owner` | string | GitHub 用户名或组织名 |
| `repo` | string | 仓库名 |
| `branch` | string | 分发分支名，默认 `dist` |
| `description` | string | 源描述 |
| `trustLevel` | string | 信任等级：`official` / `verified` / `community` / `unlisted` |
| `addedAt` | string | 添加时间（ISO 8601） |

## 信任等级

| 等级 | 含义 | 客户端行为 |
|------|------|-----------|
| `official` | 官方维护 | 直接启用 |
| `verified` | 官方审核通过 | 直接启用，标注"已认证" |
| `community` | 社区贡献 | 可用，安装插件时提示 |
| `unlisted` | 用户手动添加 | 可用，安装插件时警告 |

## 如何添加你的源

1. Fork [Template](https://github.com/UIN-Tool-Plugins/Template) 仓库
2. 按照 Template 仓库中的 README 制作插件
3. 在本仓库提交 PR，将你的源添加到 `registry.json`
4. 等待审核（`community` 级别）
