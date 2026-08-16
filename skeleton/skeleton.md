Pixel Character Engine Skeleton Definition v1.0
Fixed Character Skeleton
This skeleton is immutable.
The character body structure must never change.
The input image can only modify:
skin color
eye color
hair
clothing
accessories
The input image cannot modify:
height
width
head size
body size
leg length
face position
Canvas Definition
Canvas Size:

Width: 24 pixels
Height: 37 pixels
Coordinate system:
Origin:

Top-left corner = (0,0)

X axis:
left → right

Y axis:
top → bottom
Character Bounding Box
The character occupies:
X:
5 - 20

Y:
2 - 36
Character size:
Width:
16 pixels


Height:
35 pixels
Center axis:
X = 12
The character must remain symmetrical around the center axis.
Layer Structure
The character is divided into fixed layers:
Layer 0:
Transparent Background


Layer 1:
Shadow


Layer 2:
Accessory Extension


Layer 3:
Hair


Layer 4:
Head + Face


Layer 5:
Upper Body


Layer 6:
Lower Body


Layer 7:
Shoes
HEAD REGION
Head Mask
Fixed area:
X:
6 - 19


Y:
2 - 15
Size:
14 × 14 pixels
The head size cannot change.
FACE REGION
Fixed face area:
X:
8 - 17


Y:
6 - 12
Size:
10 × 7 pixels
The face position is locked.
EYE POSITION
Eyes must always be symmetrical.
Left Eye
X:
8 - 10


Y:
8 - 10
Size:
3 × 3 pixels
Right Eye
X:
15 - 17


Y:
8 - 10
Size:
3 × 3 pixels
Eye Rules
Both eyes must have:
same size
same shape
same color
same highlight
Forbidden:
different eye colors
different eye sizes
different positions
NOSE REGION
Fixed:
X:
12


Y:
11 - 12
Size:
1 × 2 pixels
MOUTH REGION
Fixed:
X:
11 - 13


Y:
13
Size:
3 × 1 pixels
HAIR REGION
Hair occupies:
X:
6 - 19


Y:
2 - 16
Hair may extend:
Maximum:

2 pixels outside head boundary
Allowed changes:
hair color
simple hairstyle silhouette
Forbidden:
changing head size
realistic hair strands
hair extending to body
UPPER BODY REGION
Fixed torso:
X:
6 - 19


Y:
16 - 26
Size:
14 × 11 pixels
Contains:
shoulders
clothing
arms
The torso height cannot change.
ARM REGION
Left Arm
X:
5 - 8


Y:
18 - 27
Right Arm
X:
17 - 20


Y:
18 - 27
Arm rules:
fixed length
fixed position
simple pixel shape
The pose from the photo must not change the arm skeleton.
LOWER BODY REGION
Fixed:
X:
8 - 16


Y:
27 - 34
Size:
9 × 8 pixels
Contains:
pants
skirt
legs
LEG REGION
Left leg:
X:
8 - 11


Y:
27 - 34
Right leg:
X:
13 - 16


Y:
27 - 34
Leg rules:
Forbidden:
longer legs
thinner legs
realistic proportions
SHOE REGION
Fixed:
X:
7 - 17


Y:
34 - 36
Size:
11 × 3 pixels
Shoes can change:
color
simple design
Shoes cannot change:
height
leg length
ACCESSORY EXTENSION REGION
Accessories are allowed to exceed the body.
Maximum area:
X:
2 - 22


Y:
0 - 37
Allowed:
hats
glasses
earrings
bags
hair accessories
small handheld objects
Accessories cannot modify:
skeleton
body size
character height
Skeleton Validation
Before output, check:
Canvas = 24×37

PASS


Head position unchanged

PASS


Face position unchanged

PASS


Eyes symmetrical

PASS


Body height unchanged

PASS


Leg length unchanged

PASS
Final Skeleton Rule
The skeleton is the character.

The photo is only a skin layer.

Never redraw the body.

Always fill the fixed skeleton.
