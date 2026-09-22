# AGENTS.md — AbyssBloom 协作约定

本文件供 AI 编程助手与团队成员共同阅读。任何代码改动都必须遵守以下约定。

## 项目定位

2D 增量 + 捕鱼玩法的轻量化独立游戏。美术方向：奇幻生物 + 治愈风格 + 废土质感。

## 工程基线

- 引擎：Unity **6000.0.51f1**（Unity 6），URP 17.0.3，2D Renderer
- 输入：Input System 1.11.2（**新输入系统**，不要写 `Input.GetKey` 这类旧 API）
- UI：uGUI 2.0.0 + TextMeshPro
- 语言：C#，目标框架遵循 Unity 6 默认（.NET Standard 2.1）

## 代码放置规则

| 要写的代码 | 放到 |
| --- | --- |
| 启动流程、状态机、存档、离线收益 | `Assets/_Project/Scripts/Core/` |
| 抛竿、张力、判定、鱼咬钩、稀有度抽取 | `Assets/_Project/Scripts/Fishing/` |
| 升级树、自动收益、转生循环 | `Assets/_Project/Scripts/Incremental/` |
| 货币、掉落、数值曲线公式 | `Assets/_Project/Scripts/Economy/` |
| ScriptableObject 类定义、数据加载校验 | `Assets/_Project/Scripts/Data/` |
| 界面逻辑 | `Assets/_Project/Scripts/UI/` |
| 音频、输入、本地化、对象池等横切能力 | `Assets/_Project/Scripts/Systems/` |
| 编辑器扩展 | `Assets/_Project/Scripts/Editor/` |
| 通用工具、扩展方法 | `Assets/_Project/Scripts/Utils/` |

## 硬性约束

1. **资源全部放 `Assets/_Project/`**，不要散落在 `Assets/` 根目录。
2. **第三方插件放 `Assets/ThirdParty/`**，不修改其内部代码；需要改动时用 partial class 或包装层。
3. **数据驱动优先**：鱼种、升级项、稀有度、数值曲线一律用 ScriptableObject，禁止硬编码数值到逻辑代码里。
4. **命名遵循 README 的前缀表**（`SC_` `PF_` `SO_` `T_` `SPR_` `SFX_` 等）。
5. **新增资产文件夹必须配 `.meta`**（由 Unity 生成，不要手动创建或删除 `.meta`）。
6. **不要提交** `Library/` `Temp/` `obj/` `Logs/` `UserSettings/` `Builds/`（已在 `.gitignore` 中）。
7. **增量玩法必须做好大数处理**：收益可能指数增长，采用 `double` 或自定义大数结构，并配单位缩写格式化（K / M / B / T / aa / ab …）。
8. **离线收益**必须与在线结算走同一套公式，避免双份数值逻辑漂移。

## 美术资源交接

- 源文件（PSD / Blender / AE）放 `ArtSource/`，导出成品放 `Assets/_Project/Art/`。
- 2D 精灵统一 **PNG**，带透明通道，导入设置为 `Sprite (2D and UI)`。
- 像素风与矢量风不要混用；确需混用需在 `Docs/Standards/` 记录原因。

## 提交规范

- 分支：`feature/<模块名>` → `main`
- 提交信息格式：`<类型>(<模块>): <描述>`，类型取 `feat` `fix` `art` `audio` `balance` `docs` `chore`
  - 例：`feat(fishing): 加入张力条判定窗口`
  - 例：`balance(economy): 调整一级鱼竿收益曲线`
