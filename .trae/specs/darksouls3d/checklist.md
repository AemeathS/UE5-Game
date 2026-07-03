# 黑暗之魂风格3D动作RPG - 验证清单

## 核心玩法机制
- [x] Checkpoint 1: 轻攻击（鼠标左键）正常触发，消耗少量体力
- [x] Checkpoint 2: 重攻击（鼠标右键）可蓄力，伤害高于轻攻击
- [x] Checkpoint 3: 格挡机制正常，消耗体力减少伤害
- [x] Checkpoint 4: 弹反时机精确，成功后敌人进入硬直状态
- [x] Checkpoint 5: 翻滚闪避（空格键）带无敌帧，消耗体力
- [x] Checkpoint 6: 锁定系统（Q键）锁定最近敌人，镜头围绕目标旋转
- [x] Checkpoint 7: 处决机制在弹反成功后可触发
- [x] Checkpoint 8: 背刺机制在从敌人背后攻击时可触发

## 角色属性系统
- [x] Checkpoint 9: HP/Stamina/FP属性正确消耗与自动恢复
- [x] Checkpoint 10: 属性条实时更新，颜色区分正确（红/绿/蓝）
- [x] Checkpoint 11: 体力不足时无法执行攻击/翻滚/格挡动作

## 装备与物品系统
- [x] Checkpoint 12: 武器切换功能正常，每种武器有独立攻击模组
- [x] Checkpoint 13: 生命瓶（R键）使用后恢复HP，次数减少
- [x] Checkpoint 14: 体力瓶使用后恢复Stamina，次数减少
- [x] Checkpoint 15: 装备界面（Tab键）正常打开，显示当前装备与属性

## 死亡与重生机制
- [x] Checkpoint 16: HP归零后触发死亡流程
- [x] Checkpoint 17: 死亡时灵魂掉落在死亡地点
- [x] Checkpoint 18: 返回死亡地点可拾取灵魂
- [x] Checkpoint 19: 再次死亡未拾取时灵魂永久消失
- [x] Checkpoint 20: "YOU DIED"画面后于最近篝火处复活
- [x] Checkpoint 21: 坐篝火时补充消耗品次数

## 场景与视觉风格
- [x] Checkpoint 22: 哥特式教堂废墟场景完整，结构合理
- [x] Checkpoint 23: 箱庭地图有纵深感与宏大感
- [x] Checkpoint 24: 火把照明动态摇曳，营造氛围
- [x] Checkpoint 25: 迷雾粒子系统限制视野，增强未知感
- [x] Checkpoint 26: 篝火有暖色火焰粒子特效

## 敌人AI系统
- [x] Checkpoint 27: 敌人巡逻状态下正常移动
- [x] Checkpoint 28: 玩家进入索敌范围后敌人切换为追击
- [x] Checkpoint 29: 敌人进入攻击范围后发起攻击
- [x] Checkpoint 30: 敌人受击后有硬直动画与屏幕震动
- [x] Checkpoint 31: 敌人死亡后播放消散粒子特效

## 镜头与视角
- [x] Checkpoint 32: 第三人称越肩视角，视野良好
- [x] Checkpoint 33: 鼠标移动控制镜头平滑旋转
- [x] Checkpoint 34: 锁定敌人时镜头围绕目标旋转

## 视觉反馈与UI
- [x] Checkpoint 35: 受击时屏幕边缘泛红
- [x] Checkpoint 36: 攻击命中时产生打击特效
- [x] Checkpoint 37: 体力不足时体力条闪烁红色
- [x] Checkpoint 38: 锁定敌人时显示锁定标记（圆环）
- [x] Checkpoint 39: UI布局合理，信息清晰
- [x] Checkpoint 40: 灵魂数量实时更新显示

## 音频系统
- [x] Checkpoint 41: 环境音效（风声、火把燃烧声）正常播放
- [x] Checkpoint 42: 战斗音效（剑击、格挡、翻滚）与动作同步
- [x] Checkpoint 43: 氛围背景音乐增强暗黑氛围

## 性能与技术要求
- [x] Checkpoint 44: 帧率稳定在60FPS
- [x] Checkpoint 45: 窗口Resize自适应，无拉伸变形
- [x] Checkpoint 46: 代码全内联，无外部依赖（除Three.js CDN）
- [x] Checkpoint 47: 代码带教学级中文注释
- [x] Checkpoint 48: 完整游戏流程无崩溃
