# 鲸落之后 · 术语表

> **版本**：v1.0 ｜ **日期**：2026-09-29 ｜ **负责**：策划 A
> **状态**：🔴 待全组评审 → 评审通过后升为 🟢 定稿
> **依据**：`Docs/Standards/鲸落之后_完整GDD_v1.0.md` ｜ 叙事决策 D1—D14
> **上层文档**：`narrative-design-framework.md` §2.4（本表即该节要求的交付物）

---

## 0. 这份表是干什么的

三层用途，按重要性排序：

1. **程序接口** —— 第 6 节的 Id 常量表是代码与配置的唯一来源。**本表定稿前，代码里不得出现任何专有名词的字符串。**
2. **文案纪律** —— 第 5 节「禁用同义写法」列出的东西一旦出现，视为文案错误，评审直接打回。
3. **本地化预留** —— 中英对照是首发中文单语言下也要先做的事：等要出英文时再改名，成本是现在的十倍。

### 状态标记

| 标记 | 含义 |
| --- | --- |
| 🟢 定稿 | 全组已确认，改名需走评审 |
| 🟡 推荐 | 有明确建议值，但未走过评审 |
| 🔴 待定 | **存在两个以上合理方案，需要拍板**（见第 8 节） |
| ⛔ 暂缓 | 涉及尚未回答的问题（Q9/Q12 等），先占位不定名 |

> ⚠️ **不要在正文里直接用 🔴 待定项的英文名**。程序可以按本表的值先写常量，但一旦第 8 节拍板，只改常量定义处，不改业务代码 —— 这正是先把常量集中的意义。

---

## 1. 世界观核心概念

这是全世界最重的几个词。它们决定玩家怎么理解这个灾难，改一个就会牵动全作。

| 中文 | English | 一句话定义 | 代码用名 | 出处 | 状态 |
| --- | --- | --- | --- | --- | --- |
| 余声 | **Echo** | 人类没被听见的话、被忽略的心愿、长期压下的情绪，离开人之后变成的极轻之物 | `Echo` | GDD 3.1 | 🟡 推荐 |
| 云海 | **CloudSea** | 余声在高空聚集成的、尚未落地的一整片海 | `CloudSea` | GDD 3.1 | 🟡 推荐 |
| 鲸群 / 天鲸 | **Whale / SkyWhale** | 云海孕育出的四头鲸鱼。承载情绪，不是灾难的策划者 | `Whale` | GDD 3.1 | 🟡 推荐 |
| 主鲸 | **MainWhale** | 玩家实际潜入的那一头。四头鲸同源同质，只有它参与剧情推进 | `MainWhale` | D9 | 🟡 推荐 |
| 寂静期 | **The Silence** | 从鲸群坠落到游戏当下之间的十几年。**不要用「灾后 X 年」** | `TheSilence` | D7 | 🟡 推荐 |
| 情绪空间 | **EchoRealm** | 鲸体内的记忆生态区域，即玩家探索的地图 | `EchoRealm` | GDD 3.1 | 🟡 推荐 |
| 现实层 | **Surface** | 鲸体之外的正常世界 —— 据点浮岛、浅海、退水后的陆地 | `Surface` | GDD 11.1 | 🟡 推荐 |
| 暗流 | **DarkCurrent** | 恶意在鲸体内凝结成的、会攻击人的东西。依附于小鱼形成敌对状态 | `DarkCurrent` | GDD 3.1 | 🟡 推荐 |
| 结壳 | **Crust** | 包裹在情绪外面的那层壳。首领就是结壳本身，**不是情绪的化身** | `Crust` | GDD 3.1 / 13.2 | 🔴 待定 |

### 1.1 一条容易写错的界线

> **结壳 ≠ 情绪。首领 = 结壳，不是「悲伤本人」。**

玩家打碎的是壳，不是悲伤。这句话如果在对白、图鉴文本、UI 提示里被写反，整部作品的立场就崩了（违反叙事边界第 1、2 条）。

写文案时的自检句：**「我打的是它外面那层，不是它。」**

---

## 2. 角色与阵营

| 中文 | English | 一句话定义 | 代码用名 | 出处 | 状态 |
| --- | --- | --- | --- | --- | --- |
| 拾海人 | **The Beachcomber** | 主角的名字，不是职业称号。灾后出生，从未见过陆地。全作不说话 | `Player` / `PlayerName` | GDD 3.4 / D4 | 🟢 定稿（中文）／🔴 英文待定 |
| 阿渡 | **Adu** | 据点里唯一见过陆地的人。商人、旧世界词典、玩家唯一的声音 | `Merchant` | GDD 3.4 / D14 | 🟢 定稿 |
| 浮岛居民 | **Islander** | 据点里 3—5 个只有氛围台词的居民。无支线、无名字 | `Islander` | D8 | 🟡 推荐 |
| 小人鱼 | **LittleFish** | 世界中所有会游动的奇幻生物的物种总称（友善与敌对都是它） | `Fish` | GDD 3.2 | 🟡 推荐 |
| 友善鱼 | **PeacefulFish** | 未被恶意依附、可直接收集的鱼。GDD 里也写「正常小鱼」 | `PeacefulFish` | GDD 3.2 | 🟡 推荐 |
| 敌对鱼 | **HostileFish** | 被暗流依附、发射弹幕的鱼。净化后变友善 | `HostileFish` | GDD 3.2 | 🟡 推荐 |
| 商人 | **Merchant** | 阵营字段值。与「阿渡」是同一对象，阿渡是它的具体身份 | `Merchant` | GDD 3.2 | 🟡 推荐 |

> **物种与阵营是两个字段**（GDD 3.2）。`FishSpecies` 决定它是谁，`Allegiance` 决定它现在可不可打。不要用同一个枚举表达两件事。

---

## 3. 区域与地图

四张图的名字**已定稿**，因为它们同时出现在 UI、地图、剧情文本和美术资产名里，改名成本最高。

| 中文 | English | 情绪 | 代码用名 | 状态 |
| --- | --- | --- | --- | --- |
| 泪潮旧居 | **Tideworn Home** | 悲伤 | `Region_Sorrow` | 🟢 定稿（中文）／🔴 英文待定 |
| 回响暗廊 | **Echoing Dark Corridor** | 恐惧 | `Region_Fear` | 🟢 定稿（中文）／🔴 英文待定 |
| 灼流腔室 | **Scalding Chamber** | 愤怒 | `Region_Anger` | 🟢 定稿（中文）／🔴 英文待定 |
| 远灯静海 | **Lampfar Still Sea** | 孤独 | `Region_Lonely` | 🟢 定稿（中文）／🔴 英文待定 |
| 中转站 | **Relay Station** | —— | `Node_Hub` | 🟡 推荐 |
| 据点 | **Home Island** | —— | `Scene_HomeIsland` | 🟡 推荐 |

### 3.1 内部节点代号（沿用 GDD 11.2）

| 代号 | 节点名 | 功能 |
| --- | --- | --- |
| `H` | 中转站 | 出生、安全商店、地图出口 |
| `A` | 鱼群区 | 普通战斗 |
| `B` | 回流通道 | 普通战斗、环境机关 |
| `C` | 遗迹支路 | 精英 1、潮晶节点 1、记忆线索 1 |
| `D` | 交汇区 | 普通战斗、记忆线索 2 |
| `E` | 深层入口 | 精英 2、潮晶节点 2、记忆线索 3、首领门 |
| `X` | 首领区 | 独立首领与情绪事件 |

> 节点代号只用于**灰盒阶段与内部沟通**，不得出现在玩家可见文本里。

---

## 4. 玩法机制

程序每天的变量命名来自这一节。

| 中文 | English | 一句话定义 | 代码用名 | 出处 | 状态 |
| --- | --- | --- | --- | --- | --- |
| 净化 | **Purify** | 敌鱼生命归零后失去恶意、恢复成可收集的鱼。**不是击杀** | `Purify` | GDD 06 | 🟢 定稿 |
| 弹幕 | **Barrage** | 敌方发射的、需要躲避的弹丸集合 | `Barrage` | GDD 12.1 | 🟡 推荐 |
| 弹丸 | **Projectile** | 单颗弹。与「弹幕」不是一回事 | `Projectile` | GDD 12.1 | 🟡 推荐 |
| 预警 | **Telegraph** | 攻击前给出的可辨识提示 | `Telegraph` | GDD 12.3 | 🟡 推荐 |
| 伙伴 | **Companion** | 装备在四槽里的鱼。分跟随型与附着型 | `Companion` | GDD 08 | 🟢 定稿 |
| 跟随型 | **Follower** | 游在玩家身边的伙伴表现 | `Follower` | GDD 8.1 | 🟡 推荐 |
| 附着型 | **Attached** | 化为装备上鳞片/晶体/尾鳍的伙伴表现 | `Attached` | GDD 8.1 | 🟡 推荐 |
| 伙伴槽 | **Companion Slot** | 四个装备位 | `CompanionSlot` | GDD 08 | 🟡 推荐 |
| 强化投入 | **Level** | 消耗同类鱼累积的投入值（0—10），等级由它计算得出 | `Level` | GDD 8.2 | 🟡 推荐 |
| 背包容量 | **Capacity** | 按点数计算的携带上限（12—24 点） | `Capacity` | GDD 7.1 | 🟡 推荐 |
| 体积 | **Size** | 单条鱼占用的点数（1/2/3） | `Size` | GDD 7.1 | 🟡 推荐 |
| 素体 / 基础弹 | **BaseShot** | 玩家不依赖伙伴的基础攻击 | `BaseShot` | GDD 5.3 | 🟡 推荐 |
| 自动索敌 | **AutoTarget** | 每 0.2 秒检查一次的自动选目标逻辑 | `AutoTarget` | GDD 5.2 | 🟡 推荐 |
| 闪避 | **Dodge** | 短位移 + 无敌帧 | `Dodge` | GDD 5.2 | 🟡 推荐 |
| 记忆线索 | **Memory Clue** | 每图三处的可交互叙事物件 | `MemoryClue` | GDD 11.4 | 🟡 推荐 |
| 情绪事件 | **Emotion Event** | 首领战后播放的短演出 | `EmotionEvent` | GDD 9.2 | 🟡 推荐 |
| 情绪进度 | **Emotion Progress** | 四种情绪永久找回标记 | `EmotionProgress` | GDD D16 | 🟡 推荐 |
| 本局 | **Run** | 一次「从据点出海到结束」的完整过程 | `Run` | GDD 1.1 | 🟡 推荐 |
| 返航 | **Return** | 主动结束本局回到据点 | `Return` | GDD 9.5 | 🟡 推荐 |
| 出海 | **Departure** | 从据点出发开始一局 | `Departure` | GDD 11.5 | 🟡 推荐 |

---

## 5. 货币 · 数值 · UI

这一节同时是**禁用同义写法**的执法依据 —— 右列一旦出现就是文案错误。

| 中文 | English | 定义 | 代码用名 | ❌ 禁用同义写法 |
| --- | --- | --- | --- | --- |
| 金币 | **Coin** | 局内钱包货币。死亡清零 | `Coin` | 钱、硬币、Gold、Money |
| 潮晶 | **TideCrystal** | 唯一永久货币。**只有「待存入」和「已存入」两种状态** | `TideCrystal` | 结晶、宝石、晶石、Crystal |
| 待存入潮晶 | **TideCrystal · Unbanked** | 本局携带、未结算的潮晶。死亡会全部失去 | `TideCrystalUnbanked` | 未存入潮晶、临时潮晶、「携带潮晶」 |
| 已存入潮晶 | **TideCrystal · Banked** | 首领胜利后转入局外账户、永久保留的潮晶 | `TideCrystalBanked` | 存款、账户潮晶、永久潮晶 |
| 调息台 | **Breath Altar** | 据点里购买永久属性的装置 | `BreathAltar` | 祭坛、神龛、升级台 |
| 永久属性 | **Permanent Upgrade** | 体魄 / 共鸣 / 游动 三类 | `PermanentUpgrade` | 天赋、技能树、被动 |
| 体魄 | **Vigor** | 永久属性一：最大生命 +5 | `Upgrade_Vigor` | 体质、生命、Health |
| 共鸣 | **Resonance** | 永久属性二：全部攻击 +2% | `Upgrade_Resonance` | 攻击、力量、Strength |
| 游动 | **Swim** | 永久属性三：移速 +2% | `Upgrade_Swim` | 速度、敏捷、Speed |
| 泡壳 | **BubbleShell** | 主角的手作潜水装置。**无氧气倒计时** | `BubbleShell` | 氧气瓶、潜水服、呼吸器 |
| 出海选择 | **Departure Screen** | 选起点地图的界面 | `UIDeparture` | 出发界面、地图选择 |

> ⚠️ **潮晶只有一种，两个状态。** 界面必须分开标注，但内部绝不引入第三种货币枚举 —— 这是 GDD 9.1 的硬规则。

---

## 6. 敌方与首领

| 中文 | English | 说明 | 代码/资源用名 | 状态 |
| --- | --- | --- | --- | --- |
| 追游者 | **Chaser** | 行为模板：缓慢追踪、接触伤害 | `Behavior_Chaser` | 🟡 推荐 |
| 点射者 | **Sniper** | 行为模板：保持距离、定时瞄准射击 | `Behavior_Sniper` | 🟡 推荐 |
| 扇射者 | **Fanner** | 行为模板：固定方向扇形弹幕 | `Behavior_Fanner` | 🟡 推荐 |
| 冲刺者 | **Charger** | 行为模板：预告路径后直线冲刺 | `Behavior_Charger` | 🟡 推荐 |
| 环射者 | **Circler** | 行为模板：带固定缺口的环形弹 | `Behavior_Circler` | 🟡 推荐 |
| 护伴者 | **Guardian** | 行为模板：为附近敌人提供临时护盾 | `Behavior_Guardian` | 🟡 推荐 |
| 精英 | **Elite** | 行为模板 + 第二种间隔攻击，3 倍生命 | `Elite` | 🟡 推荐 |
| 缄泪之壳 | **Hushed Shell** | 悲伤首领 | `Boss_Sorrow` | 🔴 英文待定 |
| 惊影巡游者 | **Shade Rover** | 恐惧首领 | `Boss_Fear` | 🔴 英文待定 |
| 怒潮钳冠 | **Tideclamp Crest** | 愤怒首领 | `Boss_Anger` | 🔴 英文待定 |
| 无回应之眼 | **Unanswered Eye** | 孤独首领 | `Boss_Lonely` | 🔴 英文待定 |

### 6.1 首领资源 Id 建议用功能名而非意象名

首领的中文名很有画面感，但**英文名和代码 Id 建议从「功能」出发，而不是直译意象**。理由：

- 直译会让英文名长得像诗歌，美术和程序在资产列表里认不出来是谁
- 四个首领的机制差异（停下来 / 照住它 / 给它出口 / 回应它）才是关卡设计的骨架

**建议的 Id 与资产名格式**：`Boss_Sorrow` / `Boss_Fear` / `Boss_Anger` / `Boss_Lonely`（情绪优先，避免四个名字各写一套）。
美术资产沿用 `Boss_Sorrow_Body`、`Boss_Sorrow_AttackA` 这类结构，**不要用意象英文名做前缀**。

> 待定项：四个首领的**英文显示名**要不要保留诗意。见第 8 节 O1。

---

## 7. 十二种伙伴鱼

| ID | 中文 | English（推荐） | 类型 | 体积 | 情绪 |
| --- | --- | --- | --- | --- | --- |
| `F01` | 灯鳍鱼 | **Lanternfin** | 跟随 | 1 | 悲伤 |
| `F02` | 芽背鱼 | **Sproutback** | 附着 | 2 | 悲伤 |
| `F03` | 泡灵 | **Bubblespirit** | 附着 | 1 | 悲伤 |
| `F04` | 针尾鱼 | **Needletail** | 跟随 | 2 | 恐惧 |
| `F05` | 玻璃水母 | **Glass Jelly** | 跟随 | 2 | 恐惧 |
| `F06` | 回声螺 | **Echoconch** | 附着 | 1 | 恐惧 |
| `F07` | 剪钳虾 | **Shearclaw** | 跟随 | 3 | 愤怒 |
| `F08` | 焰尾鱼 | **Emberfin** | 附着 | 2 | 愤怒 |
| `F09` | 镜鳞鱼 | **Mirrorscale** | 附着 | 2 | 愤怒 |
| `F10` | 归灯鱼 | **Homeray** | 跟随 | 3 | 孤独 |
| `F11` | 背屋蟹 | **Houseback Crab** | 跟随 | 3 | 孤独 |
| `F12` | 织潮鳐 | **Tideweaver Ray** | 附着 | 2 | 孤独 |

> 资源命名格式：`PF_Fish_Lanternfin`、`SPR_Fish_Lanternfin_Idle`、`SO_Fish_F01`。
> **配置资产用稳定 ID（`SO_Fish_F01`），贴图用英文名** —— ID 是程序接口，英文名可以后续替换。

---

## 8. 音频与音效

| 中文 | 事件名 | 说明 |
| --- | --- | --- |
| 命中 | `Play_Hit` | 友方攻击命中 |
| 受击 | `Play_Hurt` | 玩家受伤，优先级高于命中 |
| 净化 | `Play_Purify` | 敌鱼转友善 |
| 拾取 | `Play_Pickup` | 收入背包（与净化分开，防止玩家误以为击败即已入包） |
| 强化 | `Play_LevelUp` | 伙伴升级 |
| 交易 | `Play_Trade` | 售出 / 购入 |
| 潮晶存入 | `Play_Bank` | 与金币拾取明显不同 |
| 解锁 | `Play_Unlock` | 地图 / 内容解锁 |
| 死亡 | `Play_Death` | 本局结束 |

---

## 9. 程序接口：Id 常量表

**这一节是给程序的。** 建议落地方式：一个静态类，所有专有名词字符串只在这里出现一次。

```csharp
// Assets/_Project/Scripts/Data/GameIds.cs
// 术语表 v1.0 对应实现。改名前先改 Design/GDD/glossary.md。
public static class GameIds
{
    // —— 情绪（永远只用这四个，顺序即章节顺序）——
    public const string Sorrow = "sorrow";
    public const string Fear   = "fear";
    public const string Anger  = "anger";
    public const string Lonely = "lonely";

    // —— 区域 ——
    public const string RegionSorrow = "region_sorrow";
    public const string RegionFear   = "region_fear";
    public const string RegionAnger  = "region_anger";
    public const string RegionLonely = "region_lonely";

    // —— 货币（只有两种，潮晶的两个状态是字段不是枚举）——
    public const string Coin             = "coin";
    public const string TideCrystal      = "tide_crystal";
    public const string TideCrystalUnbanked = "tide_crystal_unbanked";
    public const string TideCrystalBanked   = "tide_crystal_banked";

    // —— 永久属性 ——
    public const string UpgradeVigor     = "upgrade_vigor";
    public const string UpgradeResonance = "upgrade_resonance";
    public const string UpgradeSwim      = "upgrade_swim";

    // —— 首领 ——
    public const string BossSorrow = "boss_sorrow";
    public const string BossFear   = "boss_fear";
    public const string BossAnger  = "boss_anger";
    public const string BossLonely = "boss_lonely";

    // —— 伙伴槽 ——
    public static readonly string[] CompanionSlots = { "slot_1", "slot_2", "slot_3", "slot_4" };
}
```

### 对白 Id 规则

```
DLG_<章节>_<场景>_<序号>

DLG_C1_S02_03   → 第一章 · 场景 02 · 第 3 条
```

| 段 | 取值 | 说明 |
| --- | --- | --- |
| 章节 | `C0` 序章 / `C1` 悲伤 / `C2` 恐惧 / `C3` 愤怒 / `C4` 孤独 / `C5` 结局 | 与 GDD 章节顺序一致 |
| 场景 | `S01` … `S99` | 场景卡编号，全作 20—25 个 |
| 序号 | `01` … `99` | 场景内顺序 |

### 演出 Id 规则

```
CUT_<章节>_<场景>_<级别>

CUT_C1_S05_A   → 第一章 · 场景 05 · A 级演出（全屏 ≤ 25 秒）
```

级别取 `A` / `B` / `C`，与框架 §11 的演出分级一一对应。

---

## 10. 待拍板清单

以下五项**不改玩法，但会锁死代码里的显示字符串**，建议在动笔写第一章脚本之前定掉。

| # | 问题 | 方案 A | 方案 B | 影响面 |
| --- | --- | --- | --- | --- |
| **O1** | 主角中文名 | **拾海人**（保留，D4 已定） | 给一个具体人名 | 全作对白称呼、存档字段、成就名 |
| **O2** | 主角英文名 | `Beachcomber` | `The Shorefinder` / `Tidewalker` | 本地化、代码 Id（内部仍用 `Player`） |
| **O3** | 四个首领英文显示名 | **功能直译**（Hushed Shell…） | 保留诗意译名 | 图鉴、成就、资产前缀 |
| **O4** | 四张图英文名 | 上表推荐值 | 更短的意译 | 地图 UI、资产名 |
| **O5** | 「结壳」的玩家可见叫法 | **结壳**（保留） | 直接不提名，只描述 | 首领战提示、图鉴文本 |

> **O1 / O5 优先。** O2—O4 只影响英文，首发中文单语言的情况下可以缓，但**现在定比以后定便宜**。

---

## 11. 使用纪律

| 规则 | 说明 |
| --- | --- |
| 一处写死 | 同一个设定只在本表定义一次，其他文档引用，不复制 |
| 定稿前不写字符串 | 代码里只许出现第 9 节的常量引用，**不许出现中文字面量** |
| 术语变更先改本表 | 改本表 → 升版本 → 通知程序 → 再动代码 |
| 禁用写法即错误 | 第 5 节右列出现的写法，评审直接打回，不做个案讨论 |
| 心理学术语黑名单 | 抑郁 / 创伤 / 原生家庭 / 疗愈 / 情绪价值 —— 一律不用（叙事边界） |

---

## 修订记录

| 日期 | 版本 | 改动 | 作者 |
| --- | --- | --- | --- |
| 2026-09-29 | v1.0 | 建立全表：世界观 9 项、角色 7 项、区域 6 项、机制 20 项、货币与 UI 12 项、敌方 11 项、伙伴 12 项、音频 9 项；新增第 9 节程序 Id 常量草案与对白/演出 Id 规则；列出 5 项待拍板（O1—O5） | 策划 A |
