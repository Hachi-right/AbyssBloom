# AbyssBloom（深渊绽放）

> 2D 增量（Incremental / Idle）+ 捕鱼玩法的轻量化独立游戏
> 美术方向：**奇幻生物 + 治愈风格 + 废土质感**

---

## 一、技术基线

| 项目 | 内容 |
| --- | --- |
| 引擎 | Unity **6000.0.51f1**（Unity 6） |
| 模板 | 官方 2D Cross-Platform（内含 URP 17.0.3） |
| 渲染管线 | Universal Render Pipeline (URP) 2D Renderer |
| 输入系统 | Input System 1.11.2 |
| UI | uGUI 2.0.0 |
| 工程路径 | `D:\AbyssBloom` |

**打开方式**：Unity Hub → Add → 选择 `D:\AbyssBloom` → 用 6000.0.51f1 打开。
首次打开会重建 `Library/` 缓存，耗时 3–10 分钟，属正常现象。

---

## 二、目录总览

### 工程目录（Unity 会扫描）

| 路径 | 用途 |
| --- | --- |
| `Assets/_Project/` | **团队自己的全部资源**（下划线前缀置顶，与引擎/第三方资源区分） |
| `Assets/ThirdParty/` | 第三方插件、商店资源原样存放，**不改动其内部结构** |
| `Assets/StreamingAssets/` | 需要以原始文件形式随包发布的资源（如 JSON 配置、视频） |
| `Assets/Scenes/` `Assets/Settings/` | Unity 2D 模板自带的样例场景与 URP 配置，保留不动 |
| `Packages/` | 包依赖清单 `manifest.json` |
| `ProjectSettings/` | 工程设置（Tag、Layer、画面质量、构建目标等） |

### `Assets/_Project/` 内部结构

| 路径 | 用途 |
| --- | --- |
| `Art/Characters/` | 主角、奇幻生物、NPC 的美术资源 |
| `Art/Fish/` | 鱼类图鉴资源（按稀有度或海域再分） |
| `Art/Environment/` | 废土海域、礁石、沉船残骸等场景美术 |
| `Art/Props/` | 渔具、装备、道具 |
| `Art/UI/` | 界面切图、图标、边框 |
| `Art/VFX/` | 特效贴图与材质 |
| `Art/Animations/` | 动画剪辑（.anim）与 Animator Controller |
| `Art/Shaders/` | 自写 Shader 与 Shader Graph |
| `Audio/BGM` `Audio/SFX` `Audio/Voice` | 音乐、音效、配音 |
| `Fonts/` | 字体资源与 TMP 字体资产 |
| `Prefabs/{Characters,Fish,Environment,UI}` | 按类别分放的预制体 |
| `Scenes/` | 游戏场景（主菜单、局内、图鉴等） |
| `ScriptableObjects/{Fish,Upgrades,Rarity,Balance}` | 数据驱动配置：鱼种、升级项、稀有度、数值平衡表 |
| `Scripts/` | 全部 C# 代码，按玩法域拆分（见下） |
| `Settings/` | 运行时配置资源（URP 配置、输入配置等） |

### `Assets/_Project/Scripts/` 代码分层

| 路径 | 职责 |
| --- | --- |
| `Core/` | 游戏启动流程、全局状态机、存档读写、离线收益结算 |
| `Fishing/` | 捕鱼玩法：抛竿、张力条、判定窗口、稀有度抽取、鱼咬钩逻辑 |
| `Incremental/` | 增量系统：升级树、自动收益、转生/重置循环 |
| `Economy/` | 货币、掉落产出、数值公式与曲线 |
| `Data/` | ScriptableObject 的类定义、数据加载与校验 |
| `UI/` | 各界面逻辑，与视觉层解耦 |
| `Systems/` | 横切系统：音频、输入、本地化、设置、对象池 |
| `Editor/` | 编辑器扩展工具（必须放在名为 `Editor` 的文件夹内） |
| `Utils/` | 通用工具类与扩展方法 |

> ⚠️ 约定：`Editor` 文件夹名不可更改，Unity 依此判定编辑器专用程序集。

### 工程外协作区（不参与 Unity 构建）

| 路径 | 用途 |
| --- | --- |
| `Design/GDD/` | 策划案、玩法设计文档 |
| `Design/Balance/` | 数值平衡表（Excel / 表格文件） |
| `Design/Prototype/` | 玩法原型、纸面原型、参考拆解 |
| `Design/Reference/` | 竞品截图、灵感收集 |
| `ArtSource/` | 美术源文件（PSD / AI / Blender / AE 等），**导出后才进 Unity** |
| `AudioSource/` | 音频工程源文件（DAW 工程、分轨），导出成品才进 Unity |
| `Docs/Standards/` | 团队规范（命名、提交、分支） |
| `Docs/MeetingNotes/` | 会议记录 |
| `Docs/Changelog/` | 版本日志 |
| `Builds/` | 构建产物输出目录（已被 git 忽略） |
| `Tools/` | 外部工具脚本（批处理、导出管道等） |

---

## 三、资源命名约定

| 类型 | 前缀 | 示例 |
| --- | --- | --- |
| 场景 | `SC_` | `SC_MainMenu`、`SC_FishingGround` |
| 预制体 | `PF_` | `PF_Fish_LanternJelly` |
| 材质 | `M_` | `M_WastelandWater` |
| 贴图 | `T_` | `T_Fish_LanternJelly_Albedo` |
| 精灵 | `SPR_` | `SPR_UI_ButtonGold` |
| 动画 | `ANIM_` | `ANIM_FishIdle` |
| 动画控制器 | `AC_` | `AC_PlayerRod` |
| 音效 | `SFX_` | `SFX_Splash` |
| 音乐 | `BGM_` | `BGM_AbyssTheme` |
| 数据资产 | `SO_` | `SO_Fish_LanternJelly` |
| C# 脚本 | PascalCase，与类名一致 | `FishingRodController.cs` |

**通用规则**

- 全部资源使用 **英文名**，禁止中文、空格、特殊符号；多词用下划线或 PascalCase。
- 分类用文件夹表达，不要把分类塞进文件名。
- 禁止在 `Assets/_Project/` 内直接堆放散落资源，一律归入对应子文件夹。

---

## 四、协作流程

1. `main` 分支保持可运行；功能开发走 `feature/<模块名>` 分支。
2. 美术源文件先放 `ArtSource/`，导出成品后放入 `Assets/_Project/Art/`。
3. 数值改动同步 `Design/Balance/` 与对应的 `ScriptableObjects/`。
4. 构建产物只进 `Builds/`，不入库。
5. 提交前确认没有把 `Library/`、`Temp/`、`obj/` 纳入版本控制。

详见 `Docs/Standards/`。
