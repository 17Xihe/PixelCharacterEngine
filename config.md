# Pixel Character Engine Configuration


## ENGINE PURPOSE

This engine converts uploaded human photos into fixed pixel characters.

The output character is NOT redesigned from the photo.

The photo is only a reference for:

- hair color
- eye color
- skin tone
- clothing style
- accessories


The skeleton defines the character.


---

# CORE RULE

## Skeleton Lock

The skeleton is immutable.

Never change:

- character height
- character width
- head size
- body size
- leg length
- arm position
- face position


The generated character must always use:

24 × 37 pixel skeleton template.


---

# BODY PROPORTION LOCK


## Head

Fixed:

Width:
10 pixels

Height:
14 pixels


Face:

Width:
5 pixels

Height:
6 pixels


---

## Eyes

Fixed position.

Left eye:

3 × 1 pixels


Right eye:

3 × 1 pixels


Eyes must always be symmetrical.


Same eye color.


---

## Body


Upper body:

Fixed height.

Fixed width.


Arms:

Same position.

Same length.


---

## Legs


Leg length:

Never change.


No realistic body proportion.

No long legs.


---

# PIXEL RULE


Every element must be represented by pixel blocks.


Allowed:

- square pixels
- hard edges
- limited palette


Forbidden:

- smooth gradient
- realistic rendering
- 3D
- painting style
- anti aliasing


---

# PHOTO INTERPRETATION


The photo controls ONLY:

## Hair

Allowed:

- color
- simple hairstyle


Forbidden:

- complex realistic hair


---

## Face

Allowed:

- skin color
- eye color


Forbidden:

- changing face size
- changing eye position


---

## Clothing

Clothing should be simplified from the photo.

Example:

Real jacket:

→ pixel jacket


Real skirt:

→ pixel skirt


Real accessories:

→ simple pixel accessory


Clothing does NOT change body shape.


---

# ACCESSORY RULE


Accessories may exceed skeleton boundary slightly.


Maximum extension:

2-3 pixels outside body.


Examples:

- hats
- bags
- bows
- earrings


Accessories cannot affect:

- body height
- body width
- head position


---

# OUTPUT


Generate:

ONE pixel character only.


No:

- background
- frame
- text
- watermark
- UI


Transparent background.


---

# FILE LOADING ORDER


1.

skeleton/skeleton.md


2.

skeleton/skeleton_map.md


3.

prompt/generate.txt


4.

prompt/negative.txt


5.

config.md


Follow all rules above.
