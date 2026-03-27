---
收录日期: 2026-03-27
标签: #技能编辑器 #LogicEvent #全景扫描 #参数文档
来源目录: Source/FortySix/GamePlay/Public/Ability/Logic/
关联: [[策划AI代码查询指南]] [[CreateBullet参数速查表]]
---

# LogicEvent 全景分类总表

> 项目中共有 **163 个 LogicEvent**，按功能分为以下 12 大类。
> 
> 💡 **使用方式**：遇到想实现的效果，先在本表找到候选节点，再问 AI「帮我读取 LogicEvent_XXX.h 的参数说明」获取详细配置。

---

## 🗡️ 一、伤害判定类

| LogicEvent | 说明 |
|------------|------|
| `CreateBullet` | 创建打击盒，挂载骨骼，持续时间内进行碰撞伤害判定 → [[CreateBullet参数速查表]] |
| `CreateBulletByBuff` | 通过 Buff 触发创建打击盒 |
| `DirectEffect` | 直接结算效果，不走打击盒碰撞，瞬发 |
| `LastingEffect` | 持续区域效果 |
| `HitCheck` | 命中检测 |
| `LaunchProjectile` | 发射弹体（远程弹道攻击）|
| `DestroyProjectile` | 销毁已发射的弹体 |
| `TriggerProjectileEvent` | 触发弹体事件 |
| `SandSoldierLauncher` | 沙兵发射器（特定角色技能）|
| `SimulateBulletIndex` | 模拟子弹序号 |
| `SimulateBulletInterval` | 模拟子弹间隔 |
| `BounceAttackRate` | 弹射攻击倍率 |
| `EffectToSummon` | 对召唤物施加效果 |
| `SyncHitResultToServer` | 同步命中结果到服务器 |

---

## 🛡️ 二、防御与无敌类

| LogicEvent | 说明 |
|------------|------|
| `CreateDefBox` | 创建防御盒（格挡判定区域）|
| `InvincibilityFrame` | 无敌帧（期间不受伤害）|
| `MonsterWeaponDefend` | 怪物武器防御 |
| `DefensePredictBlock` | 防御预判阻挡 |
| `Ghost` | 幽灵状态（穿透判定）|
| `BreakSkillSet` | 中断技能组 |
| `InsideShapeDetect` | 形状内部检测 |

---

## 🏃 三、移动控制类

| LogicEvent | 说明 |
|------------|------|
| `SkillMove` | 技能中的位移（沿方向移动）|
| `MoveTo` | 移动到指定位置 |
| `ForbidMove` | 禁止移动 |
| `ForbidMoveAnim` | 禁止移动动画 |
| `ForbidNetSmoothMove` | 禁止网络平滑移动 |
| `ForbidDodge` | 禁止闪避 |
| `KnockBack` | 击退效果 |
| `Jump` | 跳跃 |
| `PositionChange` | 位置改变 |
| `AvoidPenetrationMove` | 避免穿透移动 |
| `ChangeSpeed` | 改变移动速度 |
| `AddSkillDirMoveSpeed` | 增加技能方向移动速度 |
| `ChangeGravityScale` | 改变重力缩放 |
| `ChangeStepHeight` | 改变台阶高度 |
| `SetMoveMode` | 设置移动模式 |
| `CrouchAndReset` | 蹲伏并重置 |
| `SkillDodge` | 技能闪避 |
| `DodgeEffect` | 闪避效果 |

---

## 🔄 四、连招逻辑类

| LogicEvent | 说明 |
|------------|------|
| `ComboInput` | 连招输入窗口（此期间可输入下一招）|
| `ComboSwitch` | 连招切换 |
| `ComboSwitchIndex` | 连招切换序号 |
| `CanCancel` | 可打断窗口（此期间可被其他技能打断）|
| `PreInput` | 预输入（提前接收下一个操作指令）|
| `DelayCombo` | 延迟连招 |
| `CheckTransitionTryCombo` | 检查过渡尝试连招 |
| `PreSwing` | 前摇阶段 |
| `MidSwing` | 挥砍中段 |
| `PostSwing` | 后摇阶段 |
| `HitJumpSkillFlow` | 命中跳转技能流程 |
| `ChangeSkill` | 切换技能 |
| `TriggerNewSkill` | 触发新技能 |
| `TriggerSkillEvent` | 触发技能事件 |
| `UseSkillEventActions` | 使用技能事件动作 |
| `ApplyGroupSkillCD` | 应用技能组 CD |
| `ApplyOtherSkillCD` | 应用其他技能 CD |
| `EnterCooldown` | 进入冷却 |
| `BreakSkillSet` | 中断技能组 |
| `TargetWithTagBreakSkill` | 目标带有 Tag 时中断技能 |

---

## 💫 五、Buff 与状态类

| LogicEvent | 说明 |
|------------|------|
| `AddBuff` | 给目标添加 Buff |
| `AddBuffToTriggerBoxPlayer` | 给触发盒范围内的玩家添加 Buff |
| `AddTag` | 添加 Tag |
| `AddActorTag` | 添加 Actor Tag |
| `AddTagAccodingRelation` | 根据关系添加 Tag |
| `AddTimeTag` | 添加带时限的 Tag |
| `TagNotify` | Tag 通知 |
| `PostureLock` | 姿态锁定 |
| `CostStamina` | 消耗体力 |
| `StartAccumulatingPower` | 开始蓄力 |
| `TriggerMinChargeTime` | 触发最小蓄力时间 |
| `HeavyHitBehavior` | 重击行为 |
| `ChangeImpactHpRecovery` | 改变受击 HP 恢复 |
| `ForceField` | 力场效果 |
| `GiveRevive` | 给予复活 |
| `TargetRevive` | 目标复活 |

---

## 🎬 六、视觉与特效类

| LogicEvent | 说明 |
|------------|------|
| `NiagaraEffect` | 播放 Niagara 粒子特效 |
| `NiagaraEffectByCalc` | 通过计算播放 Niagara 特效 |
| `CancelNiagaraEffect` | 取消 Niagara 特效 |
| `SpawnEffectActor` | 生成特效 Actor |
| `PlayEffectWithType` | 按类型播放特效 |
| `WeaponTrial` | 武器拖尾特效 |
| `WeaponTrialName` | 武器拖尾名称 |
| `AddOverlayMaterial` | 添加叠加材质（角色闪光等）|
| `AddWaveOverlayMaterial` | 添加波浪叠加材质 |
| `WeaponAddOverlayMaterial` | 武器添加叠加材质 |
| `MaterialCurve` | 材质曲线动画 |
| `SingleMatCurve` | 单一材质曲线 |
| `SkillMatCurve` | 技能材质曲线 |
| `MaterialEffectAnim` | 材质效果动画 |
| `MatarialVectorOnBone` | 骨骼上的材质向量 |
| `SkillActorChangeShaderParam` | 技能 Actor 改变 Shader 参数 |
| `APInSkillAlphaOverride` | 技能中 Alpha 覆盖 |
| `ChangeModelAlpha` | 改变模型透明度 |
| `HideModel` | 隐藏模型 |
| `SetHideModel` | 设置隐藏模型 |
| `HideSubMesh` | 隐藏子网格 |
| `ShowSubMesh` | 显示子网格 |
| `SetMesh` | 设置网格 |

---

## 📷 七、镜头控制类

| LogicEvent | 说明 |
|------------|------|
| `CameraShake` | 镜头震动 |
| `CameraFov` | 改变视野角 FOV |
| `CameraFrameYaw` | 镜头帧偏航 |
| `CameraRotAnim` | 镜头旋转动画 |
| `CameraRotateToTarget` | 镜头旋转朝向目标 |
| `CameraSensitivity` | 镜头灵敏度 |
| `CameraSensitivityChange` | 改变镜头灵敏度 |
| `CameraZReset` | 镜头 Z 轴重置 |
| `ChangeCameraMode` | 改变镜头模式 |
| `SwitchCameraMode` | 切换镜头模式 |
| `LimitCameraPitch` | 限制镜头俯仰角 |
| `LimitCameraYaw` | 限制镜头偏航角 |

---

## 🎵 八、音效类

| LogicEvent | 说明 |
|------------|------|
| `PlaySound` | 播放音效 |
| `AkEvent` | 播放 Wwise 音效事件 |
| `AkEventMonsterHit` | 怪物被击中音效事件 |
| `AkEventState` | 音效状态事件 |

---

## 🎯 九、瞄准与目标选取类

| LogicEvent | 说明 |
|------------|------|
| `TargetChoose` | 目标选取 |
| `TargetSysSelect` | 目标系统选择 |
| `ShowTargetSysUI` | 显示目标系统 UI |
| `NewAssitAim` | 新辅助瞄准 |
| `BlurryAim` | 模糊瞄准 |
| `AttackAimAngle` | 攻击瞄准角度 |
| `AttackDirRemind` | 攻击方向提示 |
| `AttackGuide` | 攻击引导 |
| `BowAim` | 弓箭瞄准 |
| `ReloadAim` | 换弹瞄准 |
| `SetAimVisible` | 设置瞄准可见性 |
| `RotateToTarget` | 旋转朝向目标 |
| `UpdateRotation` | 更新旋转 |
| `CheckTargetPos` | 检查目标位置 |
| `TargetPlayAnim` | 目标播放动画 |

---

## 🤖 十、怪物专用类

| LogicEvent | 说明 |
|------------|------|
| `MonsterAttach` | 怪物附着 |
| `MonsterAttackWarn` | 怪物攻击预警 |
| `MonsterBeHitWindow` | 怪物受击窗口 |
| `MonsterChangeStageNotify` | 怪物阶段切换通知 |
| `MonsterSelectPoint` | 怪物选点 |
| `AimOffsetMonster` | 怪物瞄准偏移 |
| `AimRotateMonster` | 怪物旋转瞄准 |
| `ResumeMonsterAI` | 恢复怪物 AI |
| `ChangeHate` | 改变仇恨 |
| `ChangeHateToSummon` | 把仇恨转移到召唤物 |
| `SorcererBossCopySkill` | 法师 Boss 复制技能（特定 Boss）|

---

## 🔗 十一、召唤物类

| LogicEvent | 说明 |
|------------|------|
| `Summon` | 召唤 |
| `SummonDetach` | 召唤物解除绑定 |
| `LockSummon` | 锁定召唤物 |
| `CallSummonFunction` | 调用召唤物函数 |
| `AddAdditionalSkill` | 添加附加技能 |
| `ControlPuppet` | 控制傀儡 |

---

## 🔧 十二、武器与动画类

| LogicEvent | 说明 |
|------------|------|
| `WeaponMontage` | 武器蒙太奇 |
| `WeaponAnimTrigger` | 武器动画触发 |
| `WeaponWrap` | 武器缠绕 |
| `WeaponSlowSpeedEnd` | 武器慢速结束 |
| `SwitchWeaponCollision` | 切换武器碰撞 |
| `HideWeapon` | 隐藏武器 |
| `ChangeWeapon` | 切换武器 |
| `CreateDisplayWeapon` | 创建展示武器 |
| `DestroyDisplayWeapon` | 销毁展示武器 |
| `SetArrowToMesh` | 设置箭矢到网格 |
| `ReloadWeapon` | 换弹 |
| `PlayVehicleMontage` | 播放载具蒙太奇 |
| `TriggerVehicleMontage` | 触发载具蒙太奇 |
| `SkillSlotFullBodyAnim` | 技能槽全身动画 |
| `SkillFootIKRotation` | 技能脚部 IK 旋转 |
| `ChangeDynamicActionSpeed` | 改变动态动作速度 |
| `ChangeCollision` | 改变碰撞 |

---

## ⚙️ 十三、系统与其他类

| LogicEvent | 说明 |
|------------|------|
| `LuaEvent` | 调用 Lua 脚本事件（扩展能力最强）|
| `NotifyMechanism` | 通知机制 |
| `QTEPoint` | QTE 节点 |
| `QTEStage` | QTE 阶段 |
| `ClickTips` | 点击提示 |
| `CheckAttachReturn` | 检查附着返回 |
| `CheckNearCollisions` | 检查附近碰撞 |
| `ForbidNetSmoothMove` | 禁止网络平滑移动 |
| `SyncScreenEntity` | 同步屏幕实体 |
| `IsForceCalcPosition` | 强制计算位置 |

---

## 🔍 快速查找指引

遇到需求时，按以下思路找节点：

| 我想实现… | 去看哪类 |
|-----------|---------|
| 打人、造成伤害 | 第一类：伤害判定 |
| 格挡、无敌 | 第二类：防御与无敌 |
| 技能位移、禁止移动 | 第三类：移动控制 |
| 连招窗口、技能打断 | 第四类：连招逻辑 |
| 加 Buff、加 Tag | 第五类：Buff 与状态 |
| 粒子特效、材质闪光 | 第六类：视觉与特效 |
| 镜头震动、FOV | 第七类：镜头控制 |
| 音效 | 第八类：音效 |
| 锁定目标、辅助瞄准 | 第九类：瞄准与目标 |
| 怪物行为 | 第十类：怪物专用 |
| 召唤物 | 第十一类：召唤物 |
| 动画、武器切换 | 第十二类：武器与动画 |
| 特殊逻辑/Lua扩展 | 第十三类：系统与其他 |
