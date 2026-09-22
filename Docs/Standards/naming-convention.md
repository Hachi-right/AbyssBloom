# 命名规范（Naming Convention）

> 全部资源使用**英文**命名。禁止中文、空格、`-`（连字符）、特殊符号。
> 多词分隔统一用**下划线 `_`** 表达「层级」，用 **PascalCase** 表达「名称部分」。

## 前缀对照表

| 资源类型 | 前缀 | 正确示例 | 错误示例 |
| --- | --- | --- | --- |
| 场景 Scene | `SC_` | `SC_FishingGround` | `fishscene` `场景1` |
| 预制体 Prefab | `PF_` | `PF_Fish_LanternJelly` | `lantern jelly` |
| 材质 Material | `M_` | `M_WastelandWater` | `water-mat` |
| 贴图 Texture | `T_` | `T_Fish_LanternJelly_Albedo` | `lanternJelly.png` |
| 精灵 Sprite | `SPR_` | `SPR_UI_ButtonPrimary` | `btn1` |
| 动画剪辑 | `ANIM_` | `ANIM_FishSwim` | `swim anim` |
| Animator 控制器 | `AC_` | `AC_PlayerRod` | `rodcontroller` |
| 音效 | `SFX_` | `SFX_RodCast` | `收竿声` |
| 音乐 | `BGM_` | `BGM_AbyssTheme` | `theme1` |
| 数据资产 | `SO_` | `SO_Fish_LanternJelly` | `lanternjellyData` |
| 字体 | `FONT_` | `FONT_MainCN` | `字体` |
| 渲染配置 | `RP_` | `RP_2DRenderer` | `renderer2d` |
| 粒子系统预制体 | `VFX_` | `VFX_BubbleBurst` | `bubbles` |

## 贴图后缀约定

| 用途 | 后缀 | 示例 |
| --- | --- | --- |
| 基础色 | `_Albedo` | `T_Fish_X_Albedo` |
| 法线 | `_Normal` | `T_Fish_X_Normal` |
| 遮罩 | `_Mask` | `T_Fish_X_Mask` |
| 自发光 | `_Emission` | `T_Fish_X_Emission` |
| UI 九宫格 | `_UI` | `T_Panel_Wasteland_UI` |

## 文件夹命名

- PascalCase，单数形式：`Art/Characters/`（不是 `characters` 或 `Characterss`）
- 不使用 `Misc`、`Others`、`Temp`、`New Folder` 这类无意义名称
- `Editor` 文件夹名**不可更改**，Unity 依此判定编辑器专用程序集

## C# 代码命名

| 元素 | 规则 | 示例 |
| --- | --- | --- |
| 类 / 结构体 / 枚举 | PascalCase | `FishingRodController` |
| 接口 | `I` + PascalCase | `ISaveable` |
| 方法 | PascalCase | `CalculateOfflineEarnings()` |
| 属性 | PascalCase | `CurrentTension` |
| 私有字段 | `_` + camelCase | `_currentDepth` |
| 局部变量 / 参数 | camelCase | `fishWeight` |
| 常量 | PascalCase 或全大写下划线 | `MaxRodLevel` |
| 事件 | PascalCase，过去式表示已发生 | `FishCaught` |

## 脚本文件命名

- 一个文件只放一个主要类，**文件名必须与类名完全一致**：`FishingRodController.cs`
- 泛型基类：`SingletonBase.cs`
- 编辑器扩展后缀 `Editor`：`FishDataEditor.cs`，且必须位于 `Editor/` 文件夹内
