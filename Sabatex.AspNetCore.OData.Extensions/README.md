# AspNetCore OData Extensions

## Change enum routing from symbolic to numeric

```C#
public enum ObjectState
{
    New=1,
    Old=2,
    Uknown=3
}
```

### before

```C#
$filter=ObjectState eq 'New'
```

### after

```C#
$filter=ObjectState eq 1
```

### Code sample create EdmModel

```C#
using Sabatex.AspNetCore.OData.Extensions;

IEdmModel GetEdmModel()
{
    var builder = new ODataConventionModelBuilder();
    ...
    builder.AddEnumTypeAsInt(typeof(Enum Type));
    return builder.GetEdmModel();
}
```
