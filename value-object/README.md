# Value Object

A small simple object, like money or a date range, whose equality isn’t based on identity.

## Implementation example

A `Tag` can be modeled as a value object. Simple tags contain only a text label and are considered equal if the text in one tag matches the text in another. This approach is implemented below, in Typescript and C#. Follow the link of each of them for implementation details and language-specific discussions.

**Typescript** ([kaiosilveira/typescript-value-object](./typescript-value-object)):

```typescript
export default class Tag {
  private _text: string;

  constructor({ text }: { text: string }) {
    this._text = text;
  }

  get text(): string {
    return this._text;
  }

  equals(other: Tag): boolean {
    return other instanceof Tag && this.text === other.text;
  }
}
```

**C#** ([kaiosilveira/csharp-value-object](./csharp-value-object)):

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
