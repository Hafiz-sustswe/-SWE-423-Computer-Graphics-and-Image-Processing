
# Assignment on Computer Graphics
## Topic: Implementation of Bresenham's Line Algorithm Using Python

This script exemplifies **Bresenham's Line Algorithm** for line rendering in computer graphics, renowned for its precision in drawing lines on raster-based displays. It leverages integer-based calculations and decision-making logic, providing a pixel-perfect representation of lines.

**Highlights:**

- Modular code structure with distinct routines for handling various line orientations.
- Utilization of `matplotlib` for graphical illustration, enhancing comprehension.
- Supports rendering lines of both shallow and steep gradients.
- Embedded examples for immediate demonstration of capabilities.

## Demonstrations
The following instances were employed to validate the algorithm's effectiveness:

- **Comprehensive Visualization**: 

![comprehensive output](Images/output1.jpg)
![comprehensive output](Images/output2.jpg)

- **Example 1**: Drawing a line from (1,1) to (8,4) - Demonstrates handling of a mild slope, where 0 < m < 1.
![example 1 visualization](Images/Line segment (1-1_ 8-4).png)

- **Example 2**: Drawing a line from (1,1) to (4,8) - Illustrates processing of a steep slope, where m > 1.
![example 2 visualization](Images/Line segment(1-1_4-8).png)

## Handling Steep Slopes (m > 1)

To adeptly manage lines with slopes surpassing 1, the algorithm introduces the following adjustments:

Y-axis Iteration: In the conventional approach for slopes between 0 and 1 (0 < m < 1), iteration occurs along the x-axis. Yet, for steeper slopes (m > 1), iterating along the y-axis proves to be more practical. This is due to the y-coordinate changing by a constant value of 1 between successive points, whereas the x-coordinate's change may exceed 1. By iterating over the y-axis, the algorithm simplifies the arithmetic involved and guarantees that every pixel on the line is accounted for precisely once.

Swapping x and y Roles: For the usual case where the slope is less than 1 (0 < m < 1), the algorithm inverts the roles of x and y for slopes exceeding 1. Consequently, both the computation of the decision parameter and the process of pixel selection pivot around variations in the y-coordinate rather than those in the x-coordinate. This swapping ensures precise pixel selection for lines with slopes over 1 by the algorithm.

Modifying the Decision Parameter: To accommodate the switch in x and y's roles, the calculation of the decision parameter (D) is also modified. While traditionally for (0 < m < 1), (D) hinges on x-coordinate changes, for steeper slopes (m > 1), it's based on y-coordinate changes. This modification allows the decision parameter to more accurately guide the selection of the appropriate pixel at every stage of drawing the line.


- **Coordinate Interchange:** It exchanges the roles of X and Y coordinates for the endpoints. This maneuver essentially recalibrates steep inclines into gentle ones by inverting the slope to its reciprocal (1/m).
- **Decision Parameter Alteration:** For an optimal decision parameter (`p`), the formula is modified to `p_new = 2 * dx - dy`, reflecting the coordinate swap and slope inversion. For standard scenarios, the decision parameter (`p`) is refined as `p_new = p + 2 * dx - 2 * dy`.

These refinements guarantee the precise enumeration of intermediary points across all inclinations, preserving the algorithm's inherent accuracy and simplicity.


## Written By : Md Sadman Hafiz , Dept. Of Software Engineering, IICT, SUST

## Reg No : 2018831057

