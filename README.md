
[Ref: Working with Cube Data Sources](https://help.tableau.com/current/pro/desktop/en-us/cubes.htm)
## Tableau Desktop: Working with Cube Data Sources

### Instructions for Using Parameters to Filter a Dashboard in Tableau with Cube Data Sources

 **Cube Data Sources**: When working with cube data sources, certain functions and features may be limited. Using parameters and calculated fields creatively can help overcome these limitations.


### Step 1: Create a Parameter

1.  **Go to**  `Data`  >  `Create Parameter`.
2.  **Name it**  `Sheet Selector`.
3.  **Set the data type to**  `String`.
4.  **Add the values**:  `sheet 1`,  `sheet 2`, and  `all`.

### Step 2: Create a Calculated Field

1.  **Go to**  `Analysis`  >  `Create Calculated Field`.
2.  **Name it**  `Sheet Filter`.
3.  **Use the following formula**:
    
    SQL
    
    ```sql
    IF [Sheet Selector] = 'sheet 1' THEN 1
    ELSEIF [Sheet Selector] = 'sheet 2' THEN 2
    ELSEIF [Sheet Selector] = 'all' THEN 3
    END
    
    ```

    
    **Description**: This calculated field converts the string values from the parameter into integers, which can be used for filtering.

### Step 3: Apply the Calculated Field as a Filter

1.  **Go to each sheet you want to swap**.
2.  **Drag the**  `Sheet Filter`  **calculated field to the Filters shelf**.
3.  **Set the filter to match the corresponding integer value**.
    -   For  `sheet 1`, set the filter to  `1`.
    -   For  `sheet 2`, set the filter to  `2`.
    -   For  `all`, set the filter to  `3`.

### Step 4: Add the Parameter Control to the Dashboard

1.  **Drag the**  `Sheet Selector`  **parameter to the dashboard**  to allow users to select which sheet to display.
    -   **Description**: This parameter control will enable users to switch between different sheets based on their selection.
