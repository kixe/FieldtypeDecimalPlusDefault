# FieldtypeDecimalPlusDefault

Field that stores a decimal number. Extension of the core fieldtype **FieldtypeDecimal** with an option to define a default value.

### IMPORTANT!
This module is mainly made to point on a core Inputfieldtype issue.

### Actual behavior <small>(core)</small>
All core number Inputfieldtypes using the same rendering function:

`InputfieldInteger::render()`

If an init or default value is provided, it will be always converted to int. So currently there is no option to define default values with decimal places.

### Workaround <small>(this module)</small>
Instead of creating a complete new Inputfieldtype used by this Fieldtype this module uses a *dirty* `afterHook()` in `InputfieldInteger::render()` to modify the value attribute of the HTML input element.

### Suggestion
Update core **InputfieldFloat** and / or **InputfieldInteger** to allow default values with decimals. In a second step number fieldtypes could include an option to define a default value.