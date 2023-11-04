# Value Object

A small simple object, like money or a date range, whose equality isn’t based on identity.

## Implementation example

A `Tag` can be modeled as a value object. Simple tags contain only a text label and are considered equal if the text in one tag matches the text in another. This approach is implemented below in C#.

```csharp
public class Tag
{
  public string Text { get; private set; }
  public Tag(string text)
  {
    this.Text = text;
  }

  public override bool Equals(object? obj)
  {
    if (obj == null) return false;

    try
    {
      var anotherTag = (Tag)obj;
      return this.Text == anotherTag.Text;
    }
    catch (InvalidCastException)
    {
      return false;
    }
  }

  public override int GetHashCode()
  {
    if (String.IsNullOrEmpty(this.Text)) return 0;
    return this.Text.GetHashCode();
  }
}
```

Visit [the poeaa-value-object](https://github.com/kaiosilveira/poeaa-value-object) repository page for implementation details and language-specific discussions.
