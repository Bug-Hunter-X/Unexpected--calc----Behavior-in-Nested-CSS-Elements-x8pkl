# Unexpected `calc()` Behavior in Nested CSS Elements

This repository demonstrates an uncommon CSS bug related to the `calc()` function when used within nested elements. The percentage in `calc()` is relative to the parent element's size, which might not be the final rendered size, especially when padding or borders are involved. This can lead to unexpected layout issues.

## Bug Description
The example shows a container with padding. A nested element attempts to use `calc()` to occupy the remaining space after subtracting a fixed pixel value. However, because `100%` is relative to the container's *content* area (before padding), the calculation is incorrect. 

## Solution
The solution uses `box-sizing: border-box` on the parent element. This ensures the padding is included in the total width calculation, leading to the expected result.