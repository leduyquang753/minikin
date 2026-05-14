# Minikin usage notes

Minikin barely has any documentation. This file contains some usage notes that have taken a painful time to figure out.

- When creating a `MinikinPaint`, make sure to set `scaleX` to say `1`. Without it, the text won't be shaped properly;
  for example, it won't have kerning applied.