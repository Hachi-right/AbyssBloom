# 分支与提交规范（Git Workflow）

## 分支模型

| 分支 | 用途 | 规则 |
| --- | --- | --- |
| `main` | 稳定主线 | 任何时候都必须能正常打开、编译、运行 |
| `feature/<模块名>` | 功能开发 | 例：`feature/fishing-tension`、`feature/upgrade-tree` |
| `art/<内容>` | 美术资源批次 | 例：`art/fish-set-01` |
| `balance/<内容>` | 数值调整 | 例：`balance/rod-curve` |
| `hotfix/<内容>` | 紧急修复 | 从 `main` 拉出，修完直接回合 |

> 美术与数值单独开分支再合并，避免大批二进制文件与代码提交混在一起难以回滚。

## 提交信息格式

```
<类型>(<模块>): <描述>
```

| 类型 | 含义 |
| --- | --- |
| `feat` | 新功能 |
| `fix` | 修复缺陷 |
| `art` | 美术资源 |
| `audio` | 音频资源 |
| `balance` | 数值调整 |
| `docs` | 文档 |
| `chore` | 构建、依赖、杂务 |
| `refactor` | 重构，行为不变 |

示例：

```
feat(fishing): 加入张力条判定窗口与完美收杆奖励
fix(save): 修复离线收益在跨天时重复结算
balance(economy): 下调一级鱼竿基础收益 12%
art(fish): 新增 8 种深海废土鱼种立绘
```

## Unity 项目特别注意

1. **`.meta` 文件必须与资源同一次提交**，否则会导致 GUID 丢失、引用断裂。
2. 提交前用 `git status` 确认没有 `Library/`、`Temp/`、`obj/`、`Builds/` 被意外纳入。
3. 场景（`.unity`）与预制体（`.prefab`）的合并冲突难以人工解决，**同一场景同一时间只由一人编辑**，通过沟通排班避免。
4. 大文件（>50MB）不要直接入库，应放工程外的 `ArtSource/` 或使用 Git LFS。

## 提交前自检清单

- [ ] Unity 控制台无报错（Warning 需评估）
- [ ] 场景与预制体引用没有出现 `Missing (Mono Script)` / `Missing Prefab`
- [ ] 新增资源的 `.meta` 已一并提交
- [ ] 提交信息符合上述格式
- [ ] 没有把源文件（PSD / BLEND / AEP）放进 `Assets/`
