# Pixel Character Engine - Dynamic Skeleton Mapping System

## 核心原则

本骨架系统用于将真实人物照片转换为像素角色。

骨架不是固定人物模板，而是一个动态参考框架。

目标：

- 保留照片中的人物姿态
- 保留身体比例差异
- 保留服装轮廓
- 保持统一像素风格

禁止：

- 强制所有角色使用同一种姿势
- 强制所有角色保持相同身体比例
- 将人物转换成默认NPC站姿


---

# 1. Pixel Grid Structure

角色最终映射到32×32像素网格。

网格仅用于：

- 控制像素比例
- 定位身体区域
- 保持视觉一致性

不是：

- 固定身体坐标
- 固定动作模板


---

# 2. Dynamic Body Skeleton

## Head（头部区域）

参考范围：

高度：
约占角色总高度的20%-30%

宽度：
约占角色总宽度的20%-35%


识别：

- 脸部朝向
- 发型轮廓
- 帽子/头饰
- 刘海位置


规则：

根据照片自动调整头部大小。

禁止：

所有角色使用相同头部尺寸。


---

# 3. Hair Mapping（头发映射）

优先级：

高于身体模板。


需要保留：

- 长度
- 颜色
- 发量
- 刘海形状
- 卷曲程度
- 绑发方式


像素化方式：

将真实头发转换为：

- 大色块
- 明暗层级
- 像素边缘


禁止：

自动替换成默认短发。


---

# 4. Torso（身体区域）

身体区域根据照片动态调整。


识别：

- 肩宽
- 身体倾斜角度
- 衣服轮廓
- 上衣长度


允许变化：

- 宽松衣服
- 修身衣服
- 外套
- 裙装


禁止：

强制统一成标准躯干。


---

# 5. Arm Mapping（手臂）

手臂必须根据照片姿态生成。


识别：

- 手臂方向
- 弯曲角度
- 手的位置


例如：

照片中：

手举起

↓

像素角色：

保持举手动作


照片中：

双手放身体两侧

↓

保持自然垂放


禁止：

所有角色默认双手垂直。


---

# 6. Hand Mapping（手部）

手部采用简化像素表达。


目标：

避免：

- 多手指
- 多手臂
- 奇怪连接


规则：

手不是重点细节区域。

优先保证：

- 数量正确
- 位置正确
- 动作正确


禁止：

为了细节增加额外手指。


---

# 7. Leg Mapping（腿部）

根据照片自动判断：

- 腿长比例
- 站姿
- 坐姿
- 行走姿态


保持：

- 裤子形状
- 裙子长度
- 鞋子类型


禁止：

自动转换成默认双腿直立姿势。


---

# 8. Pose Preservation（姿态保持）

姿态优先级：

★★★★★


必须保留：

- 身体倾斜
- 手势
- 头部方向
- 重心位置


生成流程：

照片姿态

↓

提取关键点

↓

映射到32×32骨架

↓

像素化


不要：

先生成标准人物，再套照片。


---

# 9. Skeleton Priority Order

人物转换优先级：

Priority 1:
照片姿态

Priority 2:
人物外观特征

Priority 3:
服装轮廓

Priority 4:
32×32像素比例

Priority 5:
像素艺术优化


---

# 10. Skeleton Validation Check

生成后检查：

✓ 是否保持原照片动作

✓ 是否保持头发特征

✓ 是否保持衣服类型

✓ 是否保持人物比例

✓ 是否出现默认NPC站姿

如果出现：

- 双手垂直
- 正面站立
- 固定姿势

则重新调整骨架映射。


---

# Final Rule

Skeleton is a flexible mapping framework.

It controls consistency of pixel style.

It does NOT replace the original person's pose, appearance, or clothing.
IMMUTABLE RULE
最高规则：
Skeleton never changes.

Photo only fills pixels.

Do not resize character.
