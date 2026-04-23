# Recyclable Scroll - Reusing UI Elements

<p align="center">
<img src="Assets/_RecyclableScroll/Images/recyclable-scroll-vertical-gif.gif" width="45%" />
<img src="Assets/_RecyclableScroll/Images/recyclable-scroll-horizontal-gif.gif" width="45%" />
</p>

### **Key Features**

- High Performance: Only creates the minimum number of objects necessary to fill the viewport.
- Support for large datasets: Can display lists of up to thousands of items without increasing resource consumption.
- Easy integration: Based on Unity UI’s standard ScrollRect, the source code can be customized to suit individual preferences.

### **Comparison with Traditional Methods**

| **Criteria** | **Traditional Scroll** | **Reusable Scroll** |
| --- | --- | --- |
| **Number of Objects** | Equal to the total amount of data → the more data, the more objects. | Fixed, typically twice the number visible in the viewport. |
| **RAM usage** | Increases gradually with data | Low and stable |

### **Operating principle**

- Pagination: Uses the `pageIndex` variable to control data boundaries.
- Scrolling: When *content* reaches the edge of the *viewport*, it is moved to the appropriate position to allow further scrolling (while updating the displayed data).

### **Quick Setup Guide**

1. Attach the`RecyclableScrollVertical.cs` / `RecyclableScrollHorizontal.cs` script to the *GameObject* containing the *ScrollRect* (you can place it elsewhere too 😅).
2. Drag the`ScrollRect` and `ContentRT` variables for `RecyclableScrollVertical.cs` / `RecyclableScrollHorizontal.cs` onto the Inspector window. Set the maximum number of list items to display in `TotalItems` (or set it via code). Other variables visible in the Inspector will update automatically.
3. Configure the UI items in the list as child objects of the *Content* game object (make sure the number is just enough to fill the viewport).
4. Configure `RecyclableScrollVertical.cs` / `RecyclableScrollHorizontal.cs` using the `Init()` function with a callback function as a parameter to update the data. See the sample script `ItemLoader.cs` and the sample scene *Scene_RecyclableScroll* in *Samples*.
5. Retrieve the list of UI items in*the Content* using the `TryGetComponentsInContentChildren()`  function. See the sample script`ItemLoader.cs`and the sample scene *Scene_RecyclableScroll* in *Samples*.