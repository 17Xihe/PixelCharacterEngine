# PixelCharacterEngine Skill


## NAME

Pixel Character Engine


## PURPOSE

Convert user uploaded photos into a fixed-size pixel character.

The generated character must follow the predefined skeleton system.

The character is not recreated based on human body proportions.

The skeleton is always fixed.


---

# WORKFLOW


When user uploads a photo:


## Step 1

Load configuration:

config.md


Read all immutable rules.


---

## Step 2

Load skeleton:

skeleton/skeleton.md
skeleton/skeleton_map.md


The skeleton defines:

- height
- width
- head position
- face position
- body position
- arm position
- leg position
- shoe position


Never modify skeleton.


---

## Step 3

Analyze uploaded photo.


Extract only:


### Face

- skin tone
- eye color


### Hair

- hair color
- simple hairstyle


### Clothing

Convert real clothing into simple pixel clothing.


### Accessories

Convert important accessories into pixel elements.


---

## Step 4

Load generation prompt:


prompt/generate.txt


Apply generation style.


---

## Step 5

Apply negative rules:


prompt/negative.txt


Prevent:

- realistic style
- changed proportions
- smooth rendering
- extra background


---

# ABSOLUTE RULES


The output character MUST:


✓ keep fixed height

✓ keep fixed width

✓ keep fixed head size

✓ keep fixed body size

✓ keep fixed leg length

✓ keep fixed face coordinates

✓ keep symmetrical eyes


The photo can ONLY change:


✓ colors

✓ clothing appearance

✓ simple hair

✓ accessories


---

# OUTPUT FORMAT


Generate:

One pixel character.


Background:

Transparent.


Do not generate:

- frame
- UI
- text
- watermark
- environment


---

# QUALITY CHECK


Before output verify:


□ Same height as skeleton

□ Same width as skeleton

□ Same head/body ratio

□ Same eye position

□ Same leg length

□ Pixel blocks only


If any condition fails:

Regenerate.

# FINAL VALIDATION


Before output check:


BODY:

□ Height unchanged

□ Width unchanged

□ Head ratio unchanged


FACE:

□ Eyes symmetrical

□ Same eye color


PIXEL:

□ Every element is pixel block

□ No smooth details


If any rule fails:

Regenerate.
