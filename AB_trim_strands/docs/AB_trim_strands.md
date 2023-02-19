# `trim_strands v1.4`

Trims a strands from either end, the cut can then be offset per strand which will repeat to the other side using the settings.
This compound will generate a 'point_u' attribute. A 0 - 1 value from the start to the end of the strand if it doesnt exist already.
If 'point_length' exists it will be normalised to create a 'point_u' per strand or for the object as a whole.

Currently the compound will transfer color and point_size if it exists otherwise it will give default size and color.
Point positions are kept but the end positions are generated.

To wieght values per strand, use a weight array based on the number of strands and not all point positions. For example a position array based on the strands pivot which is the same length
and order of the strand count can be used to weight per strand with position based noise or a volume weight object.

## Inputs

### `strand_geometry`
An Amino::Object input for strand geometry. It can not use an array of objects and must be merged strands.

## Settings

### `U_first`
This is the start of the strand cut value per strand. Auto port that is meant for float or array<float> values. This port is being clamped from 0 - 1.

### `U_second`
This is the end of the strand cut value per strand. Auto port that is for float or array<float> values. This port is being clamped from 0 - 1.

### `U_offset`
Auto port that is for float or array<float> values. This port reverses the direction when in the negatives.

### 'U_wrap;
Turn this on to make the trim continue to the beginning of the strand.

### 'Use_point_length'
If a point length has been set up for the whole strand object like a tree for example. Turn this on so that the object is trimmed as a whole and not per strand.

### 'default_color'
This is the default color of the strand output if there is no color geo property already set on the incoming strands.

## Random Settings

### `U_offset_random`
This offsets per strand randomly in a positive or negative direction. Auto port that is for float or array<float> values. 

### `U_first_random`
This offsets the start of the cut per strand randomly in a positive or negative direction. Auto port that is for float or array<float> values. 

### `U_second_random`
This offsets the start of the cut per strand randomly in a positive or negative direction. Auto port that is for float or array<float> values. 

### `seed`
This seed value changes the values for the random settings.

