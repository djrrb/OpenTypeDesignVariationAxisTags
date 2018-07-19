# Proposal: Linear Weight axis ('lwgt')

## Administrative Information

**Proposers name:** David Jonathan Ross

**Vendor affiliation:** DJR / Type Network

**Proposal name:** Linear weight

**Date of submission:** 19 July 2018

**New or revised proposal:** New

**Previous revision date:** N/A


## General Technical Information

**Overview:** Because the weight axis (`wght`) is meant to interact with established CSS `font-weight` conventions (400 = regular, 700 = bold), this axis may be forced to contort itself to fit those numeric values, and those values may have no direct correlation to the relative or absolute stem weight of the font (the stem weight of a typefaces Bold is not necessarily 175% of the Regular). This can be problematic when the weight axis is not used conventional font-weight selection or emphasis, for example when the font is animated across weight or a particular stem weight must be accessed. 

In these cases, the Linear Weight (`lwgt`) axis gives users an alternative means to access the weight variations in a variable font where they can specify average stem weight in terms of per-mille-of-em values. This allows users to pinpoint specific stem weights on the axis, and offers a predictable linear progression of weights with a direct relationship between the numeric axis value and the average stem weight of the font.

**Related axes:** `wght`

**Similar axes:** `wght`, proposed `xopq`

**Axis type:** weight


## Proposed Axis Details

**Tag:** lwgt

**Name:** Linear weight

**Description:** Used to vary glyph weight with continuous linear progression.

**Valid numeric range:** any negative, zero or positive value

**Scale interpretation:** Values can be interpreted as the average stem weight (however the designer wants to define it) as it varies from the default.

**Recommended or required ‘Regular’ value:** The “average” default stem weight as per-mille-of-em.

**Suggested programmatic interactions:** Applications may choose to use the Linear Weight axis to offer direct control of stem weight, just as they do for stroke weight of vector outlines. The axis value can be multiplied by the font size to offer users an absolute stem weight measurement in points, pixels, etc. Applications may also choose to use this axis if they are animating across stem weight.

**UI recommendations:** This axis should be presented as an alternative to the weight axis.

**Script or language considerations:** None.

**Additional information:** 

## Justification

**Vendor commitments:** DJR

**Conventionality benefits:** This axis is intended to act upon the same sour. Similar to the proposed `xopq`, it is directly related to stem weight, but it is not parametric in nature.

**Interoperability benefits:** Existing alongside the `wght` axis, this axis offers users multiple ways to access the weight variations in a font.

## Additional information

Below are examples of fonts designed to offer users stem weight variations in ways that are not well-served by the `wght` axis as specified, and would benefit from offering users alternative access to the weight variations.

* **[Output Sans Hairlines](https://djr.com/notes/output-sans-hairlines-font-of-the-month/)**. The weight axis in this font is used to give users precision access to stem weights, so that they can, for example, match the stem weight across multiple font sizes or to other hairline strokes used in the design. This particular font sidesteps the problem by using the `opsz` axis to act upon stem weight, but it would be nice to offer users a way to select the stroke weight directly.

* **[Merit Badge](https://djr.com/merit-badge)**: In this font, the weight axis is primarily intended for animation purposes, which requires a linear progression in stem weight on either side of the default. The `wght` axis is balanced so that the progression of stem weight is constant on either side of the default, but this happens at the cost of having the font correspond to conventional CSS conceptions of Regular and Bold values.