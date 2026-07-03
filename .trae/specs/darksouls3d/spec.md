# 黑暗之魂风格3D动作RPG - Product Requirement Document

## Overview
- **Summary**: 使用Three.js开发一款单文件3D动作角色扮演游戏，致敬《黑暗之魂3》系列，以高难度、高回报为核心设计哲学，营造压抑、神秘的暗黑奇幻世界
- **Purpose**: 在浏览器中提供开箱即玩的Dark Souls风格游戏体验，无需额外依赖
- **Target Users**: 暗黑奇幻游戏爱好者、网页游戏玩家、开发者学习参考

## Goals
- 实现完整的战斗系统（轻攻击、重攻击、格挡弹反、翻滚闪避、锁定、处决背刺）
- 实现角色属性系统（HP、Stamina、FP）及UI显示
- 实现装备与物品系统（武器切换、消耗品、装备界面）
- 实现死亡与重生机制（篝火复活、灵魂掉落与拾取）
- 构建暗黑奇幻风格场景（哥特式教堂废墟、火把、迷雾、篝火）
- 实现敌人AI（巡逻、追击、攻击）
- 实现第三人称越肩视角与平滑镜头
- 添加环境音效、战斗音效与氛围背景音乐
- 稳定运行于60FPS，支持窗口自适应

## Non-Goals (Out of Scope)
- 多人联机功能
- 复杂的装备合成/升级系统
- 完整剧情与任务系统
- 多关卡/地图切换
- 角色创建与自定义系统
- 存档系统（除篝火复活点记忆）
- VR/手柄支持

## Background & Context
- 游戏核心设计参考《黑暗之魂3》的战斗系统与氛围营造
- 采用Three.js作为渲染引擎，原生JavaScript ES6+编写
- 单HTML文件，全内联代码，双击即可运行
- 视觉风格以纯黑主色调搭配极弱暗灰层次，营造深邃未知感

## Functional Requirements
- **FR-1**: 实现轻攻击（快速、低伤害）与重攻击（慢速、高伤害、可蓄力）
- **FR-2**: 实现格挡/弹反机制，精确时机格挡可弹反敌人攻击
- **FR-3**: 实现翻滚闪避，带无敌帧(i-frame)，消耗体力值
- **FR-4**: 实现锁定系统，按下锁定键锁定最近敌人，镜头围绕目标旋转
- **FR-5**: 实现处决/背刺，从背后或弹反成功后触发特殊处决
- **FR-6**: 实现HP/Stamina/FP属性系统，自动恢复机制
- **FR-7**: 实现武器切换（直剑、大剑、盾牌），每种有独立攻击模组
- **FR-8**: 实现消耗品使用（生命瓶、体力瓶），坐篝火补充
- **FR-9**: 实现装备界面，按Tab打开查看当前装备与属性
- **FR-10**: 实现死亡与重生机制，在最近篝火处复活
- **FR-11**: 实现灵魂掉落与拾取机制
- **FR-12**: 构建哥特式教堂废墟场景，包含火把、迷雾、篝火
- **FR-13**: 实现敌人AI（巡逻、追击、攻击状态）
- **FR-14**: 实现第三人称越肩视角，鼠标控制镜头
- **FR-15**: 实现视觉反馈（受击泛红、命中特效、锁定标记）
- **FR-16**: 实现UI界面（血条、体力条、专注条、武器图标、灵魂数量）
- **FR-17**: 实现环境音效、战斗音效与氛围背景音乐

## Non-Functional Requirements
- **NFR-1**: 稳定运行于60FPS
- **NFR-2**: 窗口Resize自适应
- **NFR-3**: 代码全内联，无外部依赖（Three.js通过CDN加载）
- **NFR-4**: 代码带教学级中文注释

## Constraints
- **Technical**: Three.js最新CDN版本，原生JavaScript ES6+，单HTML文件
- **Business**: 无预算限制，纯技术演示项目
- **Dependencies**: Three.js CDN、Web Audio API

## Assumptions
- 用户使用现代浏览器（Chrome/Firefox/Edge）
- 用户具备基础游戏操作知识（WASD移动、鼠标控制视角）
- 网络连接可用（加载Three.js CDN）

## Acceptance Criteria

### AC-1: 轻攻击与重攻击
- **Given**: 玩家装备武器，体力值充足
- **When**: 按下鼠标左键
- **Then**: 播放快速轻攻击动画，产生伤害判定，消耗少量体力
- **Verification**: `programmatic`
- **Notes**: 攻击动画特定帧产生Hitbox

### AC-2: 重攻击与蓄力
- **Given**: 玩家装备武器，体力值充足
- **When**: 按住鼠标右键
- **Then**: 开始蓄力，松开后播放慢速重攻击动画，伤害高于轻攻击
- **Verification**: `programmatic`

### AC-3: 格挡与弹反
- **Given**: 玩家装备盾牌，体力值充足
- **When**: 在敌人攻击即将命中时按下格挡键
- **Then**: 成功弹反，敌人进入硬直状态，触发处决判定
- **Verification**: `human-judgment`
- **Notes**: 弹反时机需要精确，成功后有视觉反馈

### AC-4: 翻滚闪避
- **Given**: 玩家体力值充足
- **When**: 按下空格键
- **Then**: 向移动方向翻滚，期间有无敌帧，消耗体力
- **Verification**: `programmatic`

### AC-5: 锁定系统
- **Given**: 附近有敌人
- **When**: 按下Q键
- **Then**: 锁定最近敌人，敌人身上显示锁定标记，镜头围绕目标旋转
- **Verification**: `programmatic`

### AC-6: 处决与背刺
- **Given**: 敌人处于硬直状态或玩家在敌人背后
- **When**: 靠近敌人并按下攻击键
- **Then**: 播放处决/背刺动画，造成高伤害
- **Verification**: `human-judgment`

### AC-7: 属性系统与UI
- **Given**: 游戏运行中
- **When**: 执行攻击、翻滚、格挡等操作
- **Then**: HP/Stamina/FP条实时更新，体力自动恢复
- **Verification**: `programmatic`

### AC-8: 武器切换
- **Given**: 玩家持有多种武器
- **When**: 按下对应快捷键
- **Then**: 切换到对应武器，攻击模组随之改变
- **Verification**: `programmatic`

### AC-9: 消耗品使用
- **Given**: 玩家持有消耗品
- **When**: 按下R键（生命瓶）或对应键（体力瓶）
- **Then**: 使用消耗品，恢复对应属性，剩余次数减少
- **Verification**: `programmatic`

### AC-10: 装备界面
- **Given**: 游戏运行中
- **When**: 按下Tab键
- **Then**: 打开装备界面，显示当前装备与属性
- **Verification**: `human-judgment`

### AC-11: 死亡与重生
- **Given**: 玩家HP归零
- **When**: 死亡动画播放完成
- **Then**: 屏幕渐黑显示"YOU DIED"，数秒后于最近篝火处复活
- **Verification**: `human-judgment`

### AC-12: 灵魂掉落与拾取
- **Given**: 玩家死亡
- **When**: 返回死亡地点
- **Then**: 可拾取掉落的灵魂；若再次死亡未拾取，则灵魂消失
- **Verification**: `programmatic`

### AC-13: 场景与氛围
- **Given**: 游戏场景加载完成
- **When**: 玩家在场景中移动
- **Then**: 可见火把动态照明、迷雾粒子、篝火暖色火焰
- **Verification**: `human-judgment`

### AC-14: 敌人AI
- **Given**: 场景中有敌人
- **When**: 玩家进入索敌范围
- **Then**: 敌人从巡逻状态切换为追击状态，进入攻击范围后发起攻击
- **Verification**: `programmatic`

### AC-15: 第三人称视角
- **Given**: 游戏运行中
- **When**: 移动鼠标
- **Then**: 镜头平滑旋转，跟随玩家角色
- **Verification**: `human-judgment`

### AC-16: 视觉反馈
- **Given**: 玩家受击/攻击命中/体力不足/锁定敌人
- **When**: 对应事件发生
- **Then**: 屏幕边缘泛红/命中特效/体力条闪烁/锁定标记显示
- **Verification**: `human-judgment`

### AC-17: 音频系统
- **Given**: 游戏运行中，音频设备正常
- **When**: 玩家在场景中移动/战斗/坐篝火
- **Then**: 播放环境音效、战斗音效、氛围音乐
- **Verification**: `human-judgment`

### AC-18: 性能与自适应
- **Given**: 游戏运行中，调整窗口大小
- **Then**: 帧率稳定在60FPS，画面自适应窗口
- **Verification**: `programmatic`

## Open Questions
- [ ] 具体的武器攻击模组设计细节
- [ ] 篝火的具体位置与场景布局细节
- [ ] 敌人的具体数量与分布
- [ ] 音效素材的具体来源
