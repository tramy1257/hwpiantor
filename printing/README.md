# 3D Printing Notes
All STLs are for the left side of the keyboard. Simply flip them in the slicer to print the right side

## Case
There are 2 case designs:
1. Single part case (case-1-part.stl) - No support needed
2. Two-part case - Designed so the bottom cover can be switched to a clear cover down the line
    - case-2-part-wall.stl - Needs support for top ledge or bottom ledge (default orientation). I use PETG interface layer for support with great result.

## Bottom Cover
Use the two-part case for customizable bottom cover.

To print the meshed cover like I did, update the slicing settings:
- Wall loops: 4
- Top layer: 0
- Bottom layer: 0
- Infill pattern: Whichever connected pattern that you like
- Infill density: Depends on the pattern. I set 30% for Triangles pattern