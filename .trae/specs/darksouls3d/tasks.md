# 黑暗之魂风格3D动作RPG - 实现计划

## [x] Task 1: 项目基础框架搭建
- **Priority**: high
- **Depends On**: None
- **Description**: 
  - 创建单HTML文件，引入Three.js CDN
  - 搭建基础渲染循环（Renderer、Scene、Camera）
  - 实现窗口Resize自适应
  - 添加基础输入处理（键盘、鼠标）
- **Acceptance Criteria Addressed**: AC-18
- **Test Requirements**:
  - `programmatic` TR-1.1: 页面加载后Three.js场景正常渲染，控制台无错误
  - `programmatic` TR-1.2: 调整窗口大小，画面自适应，无拉伸变形
  - `programmatic` TR-1.3: 帧率监控显示稳定在60FPS左右
- **Notes**: 使用requestAnimationFrame实现渲染循环，Three.js使用最新CDN版本

## [x] Task 2: 场景构建 - 哥特式教堂废墟
- **Priority**: high
- **Depends On**: Task 1
- **Description**: 
  - 创建主场景地面（石砌地板）
  - 构建哥特式建筑结构（拱门、柱子、墙壁）
  - 添加环境元素（高塔、断桥轮廓）
  - 实现箱庭地图设计，增强纵深感
- **Acceptance Criteria Addressed**: AC-13
- **Test Requirements**:
  - `human-judgment` TR-2.1: 场景呈现暗黑哥特风格，结构完整
  - `human-judgment` TR-2.2: 地图有纵深感与宏大感，可自由探索
  - `programmatic` TR-2.3: 场景加载完成后帧率仍稳定在60FPS
- **Notes**: 使用Three.js几何体组合构建场景，减少draw call

## [x] Task 3: 环境特效系统（火把、迷雾、篝火）
- **Priority**: high
- **Depends On**: Task 2
- **Description**: 
  - 实现火把照明（动态点光源+摇曳光影）
  - 实现迷雾粒子系统（限制视野，增强未知感）
  - 实现篝火（暖色火焰粒子特效，作为重生点）
- **Acceptance Criteria Addressed**: AC-13
- **Test Requirements**:
  - `human-judgment` TR-3.1: 火把灯光动态摇曳，营造氛围
  - `human-judgment` TR-3.2: 迷雾效果自然，限制视野范围适中
  - `human-judgment` TR-3.3: 篝火火焰粒子效果逼真，有温暖感
- **Notes**: 使用ParticleSystem实现粒子效果，注意性能优化

## [x] Task 4: 玩家角色系统（建模、属性、移动）
- **Priority**: high
- **Depends On**: Task 1
- **Description**: 
  - 创建玩家角色模型（不死骑士，铠甲+披风）
  - 实现属性系统（HP、Stamina、FP）及自动恢复
  - 实现WASD移动与跳跃
  - 实现重力与地面碰撞
- **Acceptance Criteria Addressed**: AC-7, AC-18
- **Test Requirements**:
  - `programmatic` TR-4.1: 玩家可正常WASD移动，不受地形阻挡
  - `programmatic` TR-4.2: 属性值正确消耗与恢复，无负值
  - `programmatic` TR-4.3: 重力正常，掉落地面有碰撞反馈
- **Notes**: 使用CapsuleGeometry或组合几何体构建角色，披风使用布料模拟

## [x] Task 5: 战斗系统 - 攻击与翻滚
- **Priority**: high
- **Depends On**: Task 4
- **Description**: 
  - 实现轻攻击（鼠标左键，快速低伤害）
  - 实现重攻击（鼠标右键，慢速高伤害，可蓄力）
  - 实现翻滚闪避（空格键，无敌帧，消耗体力）
  - 实现攻击判定盒（Hitbox）与伤害计算
- **Acceptance Criteria Addressed**: AC-1, AC-2, AC-4
- **Test Requirements**:
  - `programmatic` TR-5.1: 轻攻击正常播放，消耗少量体力
  - `programmatic` TR-5.2: 重攻击蓄力后伤害高于轻攻击
  - `programmatic` TR-5.3: 翻滚期间无敌帧生效，消耗体力
  - `programmatic` TR-5.4: Hitbox正确检测碰撞并造成伤害
- **Notes**: 使用AnimationMixer实现动画，攻击帧生成临时Hitbox

## [x] Task 6: 战斗系统 - 格挡/弹反与锁定
- **Priority**: high
- **Depends On**: Task 5
- **Description**: 
  - 实现格挡机制（鼠标右键，消耗体力，减少伤害）
  - 实现弹反机制（精确时机格挡，敌人硬直，可处决）
  - 实现锁定系统（Q键锁定敌人，镜头围绕目标旋转）
  - 实现锁定标记（敌人身上显示红色圆环）
  - 实现箱庭地图设计，增强纵深感
- **Acceptance Criteria Addressed**: AC-13
- **Test Requirements**:
  - `human-judgment` TR-2.1: 场景呈现暗黑哥特风格，结构完整
  - `human-judgment` TR-2.2: 地图有纵深感与宏大感，可自由探索
  - `programmatic` TR-2.3: 场景加载完成后帧率仍稳定在60FPS
- **Notes**: 使用Three.js几何体组合构建场景，减少draw call

## [ ] Task 3: 环境特效系统（火把、迷雾、篝火）
- **Priority**: high
- **Depends On**: Task 2
- **Description**: 
  - 实现火把照明（动态点光源+摇曳光影）
  - 实现迷雾粒子系统（限制视野，增强未知感）
  - 实现篝火（暖色火焰粒子特效，作为重生点）
- **Acceptance Criteria Addressed**: AC-13
- **Test Requirements**:
  - `human-judgment` TR-3.1: 火把灯光动态摇曳，营造氛围
  - `human-judgment` TR-3.2: 迷雾效果自然，限制视野范围适中
  - `human-judgment` TR-3.3: 篝火火焰粒子效果逼真，有温暖感
- **Notes**: 使用ParticleSystem实现粒子效果，注意性能优化

## [ ] Task 4: 玩家角色系统（建模、属性、移动）
- **Priority**: high
- **Depends On**: Task 1
- **Description**: 
  - 创建玩家角色模型（不死骑士，铠甲+披风）
  - 实现属性系统（HP、Stamina、FP）及自动恢复
  - 实现WASD移动与跳跃
  - 实现重力与地面碰撞
- **Acceptance Criteria Addressed**: AC-7, AC-18
- **Test Requirements**:
  - `programmatic` TR-4.1: 玩家可正常WASD移动，不受地形阻挡
  - `programmatic` TR-4.2: 属性值正确消耗与恢复，无负值
  - `programmatic` TR-4.3: 重力正常，掉落地面有碰撞反馈
- **Notes**: 使用CapsuleGeometry或组合几何体构建角色，披风使用布料模拟

## [ ] Task 5: 战斗系统 - 攻击与翻滚
- **Priority**: high
- **Depends On**: Task 4
- **Description**: 
  - 实现轻攻击（鼠标左键，快速低伤害）
  - 实现重攻击（鼠标右键，慢速高伤害，可蓄力）
  - 实现翻滚闪避（空格键，无敌帧，消耗体力）
  - 实现攻击判定盒（Hitbox）与伤害计算
- **Acceptance Criteria Addressed**: AC-1, AC-2, AC-4
- **Test Requirements**:
  - `programmatic` TR-5.1: 轻攻击正常播放，消耗少量体力
  - `programmatic` TR-5.2: 重攻击蓄力后伤害高于轻攻击
  - `programmatic` TR-5.3: 翻滚期间无敌帧生效，消耗体力
  - `programmatic` TR-5.4: Hitbox正确检测碰撞并造成伤害
- **Notes**: 使用AnimationMixer实现动画，攻击帧生成临时Hitbox

## [x] Task 6: 战斗系统 - 格挡/弹反与锁定
- **Priority**: high
- **Depends On**: Task 5
- **Description**: 
  - 实现格挡机制（消耗体力，减少伤害）
  - 实现弹反机制（精确时机触发，敌人硬直）
  - 实现锁定系统（Q键锁定最近敌人，镜头跟随）
- **Acceptance Criteria Addressed**: AC-3, AC-5
- **Test Requirements**:
  - `programmatic` TR-6.1: 格挡成功时减少受到的伤害
  - `human-judgment` TR-6.2: 弹反时机精确，成功后敌人进入硬直
  - `programmatic` TR-6.3: 锁定敌人时镜头围绕目标旋转
- **Notes**: 弹反时机窗口约100-150ms，需要精确判定

## [x] Task 7: 战斗系统 - 处决与背刺
- **Priority**: medium
- **Depends On**: Task 6
- **Description**: 
  - 实现处决机制（弹反成功后敌人进入硬直，攻击触发处决）
  - 实现背刺机制（从敌人背后攻击触发）
  - 创建处决特效（橙红色粒子爆炸）
  - 创建背刺特效（紫色粒子飞溅）
- **Acceptance Criteria Addressed**: AC-6
- **Test Requirements**:
  - `human-judgment` TR-7.1: 弹反成功后可触发处决
  - `human-judgment` TR-7.2: 从敌人背后攻击可触发背刺
  - `programmatic` TR-7.3: 处决伤害100，背刺伤害80，均高于普通攻击
- **Notes**: 处决时玩家与敌人位置需要对齐

## [x] Task 8: 装备与物品系统
- **Priority**: medium
- **Depends On**: Task 4
- **Description**: 
  - 实现武器系统（直剑、大剑、盾牌，独立攻击模组与属性）
  - 实现武器切换功能（数字键1/2/3）
  - 实现消耗品系统（生命瓶R键、体力瓶F键）
  - 实现装备界面（Tab键打开/关闭）
- **Acceptance Criteria Addressed**: AC-8, AC-9, AC-10
- **Test Requirements**:
  - `programmatic` TR-8.1: 武器切换后攻击伤害正确改变（直剑20、大剑40、盾牌10）
  - `programmatic` TR-8.2: 使用消耗品后对应属性恢复，次数减少（生命瓶+50HP、体力瓶+40体力）
  - `human-judgment` TR-8.3: 装备界面信息清晰，操作流畅
- **Notes**: 使用HTML/CSS实现装备界面UI

## [x] Task 9: 敌人AI系统
- **Priority**: high
- **Depends On**: Task 4, Task 5
- **Description**: 
  - 创建不死士兵敌人模型（CapsuleGeometry组合）
  - 实现AI状态机（巡逻、追击、攻击）
  - 实现敌人攻击与受击反馈（红色闪烁、屏幕震动）
  - 实现敌人死亡消散特效（灰色粒子爆炸）
- **Acceptance Criteria Addressed**: AC-14
- **Test Requirements**:
  - `programmatic` TR-9.1: 敌人在巡逻状态下正常移动
  - `programmatic` TR-9.2: 玩家进入索敌范围(8米)后敌人切换为追击
  - `programmatic` TR-9.3: 敌人进入攻击范围(2米)后发起攻击
  - `human-judgment` TR-9.4: 敌人死亡后播放消散粒子特效
- **Notes**: 使用状态机模式实现AI逻辑

## [x] Task 10: 死亡与重生机制
- **Priority**: high
- **Depends On**: Task 4, Task 9
- **Description**: 
  - 实现玩家死亡检测（HP归零）
  - 实现灵魂掉落机制（死亡地点掉落灵魂，金色圆环标记）
  - 实现灵魂拾取机制（靠近掉落地点2米内自动拾取）
  - 实现篝火复活机制（最近篝火处复活）
- **Acceptance Criteria Addressed**: AC-11, AC-12
- **Test Requirements**:
  - `programmatic` TR-10.1: HP归零后触发死亡流程，显示"YOU DIED"
  - `programmatic` TR-10.2: 死亡时灵魂掉落在死亡地点，创建金色圆环标记
  - `programmatic` TR-10.3: 返回死亡地点2米内自动拾取灵魂，播放拾取特效
- **Notes**: 若在拾取前再次死亡，前一次掉落的灵魂永久消失
  - `human-judgment` TR-10.4: "YOU DIED"画面后于篝火复活
- **Notes**: 灵魂掉落使用标记点，再次死亡未拾取则清除

## [x] Task 11: 第三人称视角与镜头系统
- **Priority**: high
- **Depends On**: Task 4
- **Description**: 
  - 实现越肩视角（相机位于角色后方偏上，距离6米，高度3米）
  - 实现鼠标控制镜头旋转（垂直视角限制±90度）
  - 实现镜头平滑插值（lerp）
  - 实现锁定时镜头围绕目标旋转
- **Acceptance Criteria Addressed**: AC-15
- **Test Requirements**:
  - `human-judgment` TR-11.1: 视角为越肩视角，视野良好
  - `human-judgment` TR-11.2: 鼠标移动时镜头平滑旋转
  - `programmatic` TR-11.3: 锁定敌人时镜头正确围绕目标旋转
- **Notes**: 使用球面坐标计算相机位置

## [x] Task 12: UI界面系统
- **Priority**: medium
- **Depends On**: Task 4, Task 8, Task 10
- **Description**: 
  - 实现左上角属性条（HP红色/Stamina绿色/FP蓝色）
  - 实现左下角武器图标与消耗品快捷栏
  - 实现右上角灵魂数量显示（金色）
  - 实现锁定标记（红色圆环）与受击反馈（屏幕震动）
- **Acceptance Criteria Addressed**: AC-7, AC-16
- **Test Requirements**:
  - `human-judgment` TR-12.1: UI布局合理，信息清晰
  - `programmatic` TR-12.2: 属性条实时更新，颜色正确
  - `human-judgment` TR-12.3: 锁定标记与受击反馈明显
- **Notes**: 使用HTML/CSS实现UI，避免使用Three.js Canvas叠加

## [x] Task 13: 音频系统
- **Priority**: medium
- **Depends On**: Task 1
- **Description**: 
  - 实现环境音效（风声、火把燃烧声，动态调整）
  - 实现战斗音效（剑击、格挡、翻滚、受伤）
  - 实现氛围背景音乐（低沉三角波弦乐，6秒循环）
  - 添加拾取音效和死亡音效
- **Acceptance Criteria Addressed**: AC-17
- **Test Requirements**:
  - `human-judgment` TR-13.1: 环境音效营造出压抑氛围
  - `human-judgment` TR-13.2: 战斗音效与动作同步（攻击/格挡/翻滚/受伤）
  - `human-judgment` TR-13.3: 背景音乐增强暗黑氛围
- **Notes**: 使用Web Audio API生成合成音效，避免外部依赖

## [x] Task 14: 整体整合与性能优化
- **Priority**: high
- **Depends On**: All previous tasks
- **Description**: 
  - 整合所有系统模块（战斗、装备、音频、UI等）
  - 优化性能：关闭抗锯齿、降低阴影贴图(1024x1024)、减少迷雾粒子(200)、限制像素比(1.5)
  - 添加教学级中文注释（各模块均有详细注释）
  - 测试完整游戏流程
- **Acceptance Criteria Addressed**: AC-18, NFR-4
- **Test Requirements**:
  - `programmatic` TR-14.1: 完整游戏流程无崩溃
  - `programmatic` TR-14.2: 帧率稳定在60FPS（通过性能优化实现）
  - `human-judgment` TR-14.3: 代码注释清晰，易于理解
- **Notes**: 使用渲染优化、粒子数量控制等技术提升性能
