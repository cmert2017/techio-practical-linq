[//]: # (GENERATED FILE -- DO NOT EDIT)
# Methods: Extract a single value or default

The previous two lessons had a note explaining that the `First()`, `Last()`, etc. methods would throw an exception if they couldn't return a value. The methods shown here don't throw an exception. They instead return a default value.

What value do they return? That depends on the type (`T`) of the `IEnumerable<T>` sequence. If `T` is a class type, then the default value is always `null`. If it is a struct, then the default is an instance of that struct with all its elements set to their default values.

For all other data types, there is a [table of default values available on MSDN](https://msdn.microsoft.com/en-us/library/83fhsxwc.aspx).

### FirstOrDefault() method
What do you think that this call to `FirstOrDefault()` would return?

```csharp
List<double> doubles = new List<double> { 2.0, 2.1, 2.2, 2.3 };
double whatsThis = doubles.FirstOrDefault(val => val > 2.3);
```

?[What is the value of the whatsThis variable?]
 - [x] The default value for double: 0.0D
 - [ ] 2.2
 - [ ] Nothing. The FirstOrDefault() call would throw an Exception.
 - [ ] 2.3

### LastOrDefault() method
What do you think the `LastOrDefault()` in this code would return?

```csharp
List<double> doubles = new List<double> { 2.0, 2.1, 2.2, 2.3 };
double whatsThis = doubles.LastOrDefault(val => val > 2.0 && val < 2.3);
```

?[What is the value of the whatsThis variable?]
 - [ ] The default value for double: 0.0D
 - [x] 2.2
 - [ ] Nothing. The LastOrDefault() call would throw an Exception.
 - [ ] 2.3

### ElementAtOrDefault() method
Try this one. What would the `ElementAtOrDefault(4)` call return in this code snippet?

```csharp
List<double> doubles = new List<double> { 2.0, 2.1, 2.2, 2.3 };
double whatsThis = doubles.ElementAtOrDefault(4);
```

?[What is the value of the whatsThis variable?]
 - [x] The default value for double: 0.0D
 - [ ] 2.2
 - [ ] Nothing. The ElementAtOrDefault() call would throw an Exception.
 - [ ] 2.3

### SingleOrDefault() method
`SingleOrDefault()` is a bit different from the others. If there is no element in the list that meets the criteria, then a default value is returned. If more than one value meets the criteria, then it throws an exception.

With this in mind, what do you think this would do?

```csharp
List<double> doubles = new List<double> { 2.0, 2.1, 2.2, 2.3 };
double whatsThis = doubles.SingleOrDefault(val => val > 2.1 && val <= 2.3);
```

?[What is the value of the whatsThis variable?]
 - [ ] The default value for double: 0.0D
 - [ ] 2.2
 - [x] Nothing. The SingleOrDefault() call would throw an Exception.
 - [ ] 2.3