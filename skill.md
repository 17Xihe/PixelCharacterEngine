Pixel Character Engine Skill v1.0
AI像素风小人生成系统
0. 核心目标（最高优先级）
将用户上传的人物照片转换为：
固定骨架的像素风角色 Sprite
这不是重新设计一个人物。
而是：
固定角色骨架
+
照片外观信息
=
像素小人
1. 核心原则：Skeleton First
生成顺序必须：
Step 1:
加载固定角色骨架

↓

Step 2:
锁定人体比例

↓

Step 3:
读取照片信息

↓

Step 4:
填充像素颜色

↓

Step 5:
生成最终Sprite
禁止：
照片 → AI自由绘制人物
2. 固定角色尺寸
所有人物必须使用：
Canvas:

24 × 37 logical pixels
即：
Width = 24 px
Height = 37 px
人物主体范围：
X: 5 - 20

Y: 2 - 36
人物有效尺寸：
宽度：
16px

高度：
35px
禁止：
改变高度
改变宽度
拉伸人物
缩短人物
根据真人比例调整
3. 固定人体比例
人物必须保持：
Q版二头身比例
固定：
HEAD
+
BODY
+
LEGS
禁止：
真人比例迁移：
例如：
❌ 长腿
❌ 窄肩
❌ 成年人体型
❌ 模特比例
4. 固定Skeleton坐标
HEAD头部
范围：
X:6-19

Y:2-15
尺寸：
14 × 14 px
FACE脸部
固定：
X:8-17

Y:6-12
尺寸：
10 × 7 px
Eyes眼睛
必须左右完全一致。
左眼：
X:8-10

Y:8-10
右眼：
X:15-17

Y:8-10
要求：
同尺寸
同颜色
同高光
同像素结构
禁止：
左右瞳色不同。
Nose
X:12

Y:11-12
Mouth
X:11-13

Y:13
5. 身体Skeleton
Upper Body 上半身
固定：
X:6-19

Y:16-26
尺寸：
14 × 11 px
包含：
肩膀
衣服
手臂
Arms 手臂
左：
X:5-8

Y:18-27
右：
X:17-20

Y:18-27
禁止：
根据照片动作改变。
例如：
照片：
手插口袋
生成：
固定站姿。
6. 下半身Skeleton
Legs
固定：
X:8-16

Y:27-34
Shoes
固定：
X:7-17

Y:34-36
禁止：
照片中的：
长靴
高跟鞋
长裙
改变腿长。
必须压缩到固定区域。
7. Pixel Grid规则
所有内容必须由像素格组成。
要求：
1 pixel = 1 color block
禁止：
半像素
亚像素
平滑边缘
抗锯齿
模糊
渐变
8. 外观变化规则
照片只能影响：
Skin
允许：
肤色
腮红颜色
Eyes
允许：
瞳色
禁止：
改眼睛大小
改眼睛位置
Hair
允许：
发色
简单发型轮廓
禁止：
真实发丝
复杂卷发
超出头部比例
9. Clothing Layer（服装层）
衣服：
不是模板。
必须根据照片生成。
流程：
照片衣服

↓

识别：

颜色
类型
主要结构

↓

转换为像素服装
例如：
照片：
黑色西装
生成：
固定身体区域：
黑色像素外套
+
灰色阴影
+
简单领口
照片：
长裙
生成：
固定下半身区域：
裙子颜色
+
简单裙摆
禁止：
衣服改变身体尺寸。
10. Accessory Extension Layer（配饰扩展层）
配饰允许突破主体边界。
允许：
帽子
包
耳环
发饰
项链
手机
小道具
扩展范围：
X:2-22

Y:0-37
规则：
配饰可以增加视觉范围。
但是：
不能改变：
身高
身体
头部大小
例如：
照片：
大帽子
允许：
帽子超过头部。
禁止：
扩大头。
11. 色彩系统
使用有限色板。
皮肤：
最多：
3-5色
头发：
最多：
5色
衣服：
最多：
6色
配饰：
最多：
5色
禁止：
照片级颜色数量。
12. 输出要求
默认输出：
只有一个人物Sprite
必须：
透明背景。
禁止：
背景
场景
房屋
天空
草地
UI框
文字
输出：
single pixel character only
13. 风格要求
目标：
Cute Retro Pixel Game Character
特点：
清晰像素块
游戏Sprite感觉
有限颜色
硬边轮廓
禁止：
3D
动漫立绘
高清插画
写实人物
水彩
油画
14. Negative Prompt
必须加入：
different height

different body proportion

long legs

realistic anatomy

anime body

3D render

smooth gradient

anti alias

soft painting

detailed hair strands

realistic clothing folds

background

scene

UI frame

text

15. 最终生成指令
Generate a pixel character using the fixed Pixel Character Engine skeleton.

Do not create a new character.

Use the fixed 24×37 skeleton.

Keep:

same height
same width
same head size
same body size
same leg length
same eye position

Only modify:

skin color,
eye color,
hair,
clothing,
accessories.

The photo provides appearance information only.

The skeleton never changes.

Output only one transparent pixel character sprite.
