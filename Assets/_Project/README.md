# Assets/_Project — 团队资源区

`Assets/` 下只有带 `_` 前缀的 `_Project/` 是本团队维护的资源。
其余目录（`Scenes/`、`Settings/`、`ThirdParty/`、`StreamingAssets/`）各有专属用途，见根目录 `README.md`。

## 放置规则速查

| 我有… | 放这里 |
| --- | --- |
| 一张鱼的立绘 | `Art/Fish/` |
| 一个奇幻生物的原画 | `Art/Characters/` |
| 一块废土礁石的贴图 | `Art/Environment/` |
| 一根鱼竿的图标 | `Art/Props/` |
| 一个 UI 按钮的切图 | `Art/UI/` |
| 一段水花特效序列图 | `Art/VFX/` |
| 一段鱼游动的动画剪辑 | `Art/Animations/` |
| 一个自己写的 Shader Graph | `Art/Shaders/` |
| 一首背景音乐 | `Audio/BGM/` |
| 一个收杆音效 | `Audio/SFX/` |
| 一个生物预制体 | `Prefabs/Characters/` |
| 一个可钓的鱼预制体 | `Prefabs/Fish/` |
| 一个游戏场景 | `Scenes/` |
| 一份鱼种配置 | `ScriptableObjects/Fish/` |
| 一份升级项配置 | `ScriptableObjects/Upgrades/` |
| 一份稀有度权重表 | `ScriptableObjects/Rarity/` |
| 一份数值平衡曲线 | `ScriptableObjects/Balance/` |
| 一段 C# 逻辑代码 | `Scripts/<对应模块>/` |
| 需要以原始文件形式读的 JSON | `../StreamingAssets/` |

## 禁止事项

- ❌ 在 `_Project/` 根目录直接扔文件，必须归入子文件夹
- ❌ 中文文件名、空格、特殊符号
- ❌ 把 `.psd` / `.blend` / `.aep` 等源文件放进 Unity（放工程外的 `ArtSource/`）
- ❌ 手动增删 `.meta` 文件
