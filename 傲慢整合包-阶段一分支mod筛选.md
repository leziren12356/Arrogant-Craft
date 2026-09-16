# 傲慢整合包 · 第一阶段分支 Mod 筛选

> 目标环境：Minecraft 1.21.1 / NeoForge（CurseForge 实例 `Instances/Arrogant-Craft`，现有 153 个 mod）

## 结论速览

| 分类 | 第一阶段分支 | 代表 Mod | 状态 |
|---|---|---|---|
| 科技 | 机械动力 | Create 6.0.10 + Create Crafts & Additions 1.6.0 | ✅ 已装，可直接排线 |
| 科技 | 热力 | Thermal 系列 | ⛔ 无 1.21.1 版本 → 跳过 |
| 科技 | 沉浸 | Immersive Engineering 12.4.2-194 | ✅ 已装，可直接排线 |
| 魔法 | 植魔 | Botania | ⛔ 最新仅 1.20.1-455 → 建议同热力一并挂起 |
| 魔法 | 新生魔艺 | Ars Nouveau 5.13.1 + Ars Elemental | ✅ 已装，可直接排线 |
| 魔法 | 禁忌与奥秘 | Forbidden and Arcanus 2.6.1 | ➕ 有 1.21.1 版本，需补装（+ 前置 Valhelsia Core） |

→ 阶段一实际落点为 **科技 2 条 + 魔法 2 条**。

---

## 一、科技分支

### 1.1 机械动力（✅ 已就绪）

| Mod | 文件 | 说明 |
|---|---|---|
| Create 6.0.10 | `create-1.21.1-6.0.10.jar` | 分支主 mod，自带 Ponder 教学系统 |
| Create Crafts & Additions 1.6.0 | `createaddition-1.6.0.jar` | 附属：电动机 / 交流发电机，把旋转能与 FE 电网打通 |

- Create 已内置所需前置（jar-in-jar，无需另装）：**Flywheel 1.0.6**、**Ponder 1.0.82**、**Registrate 1.3.0**
- ⚠ 注意：Create 6.0.10 在 `neoforge.mods.toml` 中声明要求 **NeoForge ≥ 21.1.219**，而当前实例 `baseModLoader` 为 **neoforge-21.1.216**。第一阶段开跑前建议把 NeoForge 升级到 ≥21.1.219。
- 包内目前没有其他 Create 附属。1.21.1 可补的联动件见 §3（**Ars Creo** 最能同时服务科技+魔法两条线）。

### 1.2 热力（⛔ 跳过）

- 本地 153 个 mod 中**没有任何 Thermal jar**。
- Thermal 系列（Foundation / Dynamics / Expansion / Integration / Endergy / Extra）尚无 1.21.1 版本 → 按既定计划跳过。
- 替代思路：第一阶段「产能」这条腿交给 **Create Crafts & Additions 的发电机**，可保持科技线闭环。

### 1.3 沉浸（✅ 已就绪）

| Mod | 文件 | 说明 |
|---|---|---|
| Immersive Engineering 12.4.2-194 | `ImmersiveEngineering-1.21.1-12.4.2-194.jar` | 分支主 mod（多方块、线缆、矿物处理） |
| Just Enough Immersive Multiblocks 1.0.6 | `jeimultiblocks-1.21.1-1.0.6.jar` | JEI 内预览 IE 多方块结构（依赖 IE + JEI，均已装） |

- IE 已内置 JiJ：BlockModelSplitter 2.0.1、DualCodecs 0.1.2
- 必需前置：无（JEI 已装）

---

## 二、魔法分支

### 2.1 植魔（⛔ 建议挂起）

- 本地未安装；查官方发布记录，Botania 最新 release 为 **release-1.20.1-455**（1.20.x 分支），**没有 1.21.1 构建** → 与热力情况相同，建议一并挂起。
- 一旦移植，前置已全部就绪：**Patchouli 93**、**Curios 9.5.1**。

### 2.2 新生魔艺（✅ 已就绪）

| Mod | 文件 | 说明 |
|---|---|---|
| Ars Nouveau 5.13.1 | `ars_nouveau-1.21.1-5.13.1.jar` | 分支主 mod（法术合成、仪式、魔源自动化） |
| Ars Elemental 0.7.10.1 | `ars_elemental-1.21.1-0.7.10.1.jar` | 附属：元素系法术与装备 |
| Ars Énergistique 2.1.1-beta | `arseng-2.1.1-beta.jar` | Ars × AE2 互联，**建议放到第二阶段 AE2 解锁**，作为跨阶段奖励 |

- Ars Nouveau 内置 JiJ：Infiniverse、LambDynamicLights API、Nuggets
- 前置均已安装：**GeckoLib 4.9.2**、**Curios 9.5.1**、**Patchouli 93**

### 2.3 禁忌与奥秘（➕ 需补装）

| Mod | 建议文件 | 说明 |
|---|---|---|
| Forbidden and Arcanus 2.6.1 | `forbidden_arcanus-1.21.1-2.6.1.jar` | 分支主 mod，NeoForge 1.21.1 可用（2025-08-11 发布） |
| Valhelsia Core 1.1.4（必需前置） | `valhelsia_core-neoforge-1.21.1-1.1.4.jar` | Forbidden and Arcanus 的必需 API |

- 联动点：FA 2.6.1 的更新日志专门修复了「未安装 Ponder 时崩溃」，说明它与 **Create 6 的 Ponder** 有集成；另外包内已有 **ProjectE**，可再补 `ProjectE: EMC for Forbidden Arcanus`（1.21.1）打通 EMC。

---

## 三、可选补装清单（均已确认有 1.21.1 / NeoForge 版本）

| Mod | 关联对象 | 用途 |
|---|---|---|
| Ars Creo | Ars Nouveau × **Create** | 把机械动力与新生魔艺串成一条跨系联动（阶段一最推荐的补充） |
| Ars Additions | Ars Nouveau | QoL 小功能、存储类补充 |
| Reliquified Ars Nouveau | Ars Nouveau × **Relics** | 包内已有 Relics，做饰品（Curios）向扩展 |
| Ars Ocultas | Ars Nouveau × **Occultism** | 包内已有 Occultism |
| Modular Machinery Reborn Ars Nouveau | Ars Nouveau × **MMR** | 包内已有 Modular Machinery Reborn，可做自定义多方块 |
| Ars Polymorphia | Ars Nouveau × **Polymorph** | 配方冲突选择支持 |
| Ars Nouveau's Flavors & Delight | Ars Nouveau × **Farmer's Delight** | 食物线扩展 |
| Ars Unification | Ars Nouveau × 其他科技 mod | 让 Ars 直接复用其他 mod 的配方，非常适合做「阶段门槛」 |
| ProjectE: EMC for Forbidden Arcanus | Forbidden and Arcanus × **ProjectE** | 给禁忌与奥秘材料加上 EMC |

---

## 四、待办

1. **补装** Forbidden and Arcanus 2.6.1 + Valhelsia Core 1.1.4（mods 数量 153 → 155）。
2. **挂起** 热力、植魔两条分支，等 1.21.1 移植（或改用其他 mod 顶替该分支定位）。
3. **升级 NeoForge** 至 ≥21.1.219，避免 Create 6.0.10 的版本校验问题。
4. 阶段一最终形态：
   - 科技：机械动力 → 沉浸（两条平行线，互不为前置）
   - 魔法：新生魔艺 → 禁忌与奥秘（两条平行线）
5. 可选：加入 **Ars Creo**，让「机械动力 × 新生魔艺」在阶段一就形成一条横向联动支线。
