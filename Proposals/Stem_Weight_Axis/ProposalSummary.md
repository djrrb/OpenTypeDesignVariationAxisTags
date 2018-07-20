# Proposal: Stem Weight axis ('stem')

## Administrative Information

**Proposers name:** David Jonathan Ross

**Vendor affiliation:** DJR / Font of the Month Club

**Proposal name:** Stem Weight

**Date of submission:** 20 July 2018

**New or revised proposal:** New

**Previous revision date:** N/A


## General Technical Information

**Overview:**  The weight axis (`wght`) is intended to correspond to conventional CSS `font-weight` values, even though these values do not necessarily reflect the relative or absolute weight of the font itself. For example, even if Regular=`400` and Bold=`700`, this does not mean that any measured weight of the Bold is 175% thicker than the Regular.

Because the weight axis can stretch or contort itself to follow predefined CSS values, it can be a problem when users wants to specify weight in terms of a particular glyph measurement, or to animate the axis so that the stroke thickness grows at a predictable and consistent rate.

The Stem Weight (`stem`) axis provides an alternative way for users to access weight variations by specifying an average stem weight or stroke thickness in terms of per-mille-of-em values, as determined by the typeface designer. This axis can take the shapes already controlled by the `wght` axis and give users the ability to pinpoint a specific thickness in the designspace or travel across it with a progression of stem weight. Font developers can choose the best method for determining “average stem weight” depending on the font’s design; whether it maps to a universal stroke thickness, the average apparent weight of its characters, or the exact weight of a salient feature in the design.

**Related axes:** `wght`

**Similar axes:** `wght`, `xopq` (as proposed)

**Axis type:** weight


## Proposed Axis Details

**Tag:** stem

**Name:** Stem Weight

**Description:** Used to vary glyph weight using numeric values related to the stroke thickness and a continuous linear progression.

**Valid numeric range:** any zero or positive value

**Scale interpretation:** Values can be interpreted as the average stem weight or stroke thickness, as determined by the typeface designer. For example, in a Latin font, one might use the vertical stem of the H as a basis for the value.

**Recommended or required ‘Regular’ value:** The “average” default stem weight as per-mille-of-em.

**Suggested programmatic interactions:** Applications may choose to use the Stem Weight axis to offer direct control of stem weight, just as they do for stroke weight of vector outlines. The axis value can be multiplied by the font size to offer users an absolute stem weight measurement in points, pixels, etc. Applications may also choose to use this axis if they are animating across stem weight.

**UI recommendations:** This axis should be presented as an alternative to the Weight axis. 

**Script or language considerations:** None.

## Justification

**Vendor commitments:** DJR

**Conventionality benefits:** This axis can have the same glyph variations as `wght`. It is similar to the proposed `xopq` in that it is has a direct relationship to the measured stem weight in a font, but unlike `xopq` it is not parametric in nature and other transformations can occur on the axis.

**Interoperability benefits:** Existing alongside the `wght` axis, this axis offers users multiple ways to access the weight variations in a font. It also allows software to match stem weight across fonts.

## Additional information

Below are examples of fonts designed to offer users stem weight variations in ways that are not well-served by the `wght` axis as specified and would benefit from an alternative.

* **[Output Sans Hairlines](https://djr.com/notes/output-sans-hairlines-font-of-the-month/)**. This font is intended to give users access to precise stem weights, so that they can, for example, match the stem weight across multiple font sizes or to other hairline strokes used in the design. This particular implementation sidesteps the problem by using the `opsz` axis instead of `wght`, but it would be nice to offer users a way to select the stroke weight directly, just as they would select the stroke weight of a shape or path. This same concept could be applied to a design with stroke contrast as well.

* **[Merit Badge](https://djr.com/merit-badge)**: In this font, the `wght` axis is primarily intended for animation purposes, which relies a consistent progression of stem weight on either side of the default so there are no “bumps” in the animation. The `wght` axis is balanced on either side of the default so that there is a consistent rate of growth, but this happens at the cost of having the font correspond to conventional CSS conceptions of Regular and Bold.