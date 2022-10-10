# Value Object

A small simple object, like money or a date range, whose equality isn’t based on identity.

## Implementation examples

Find below examples of a `Tag` class implemented as a value object in different languages. For further implementation details, make sure to follow the link to each specific implementation:

**Typescript** ([kaiosilveira/typescript-value-object](https://github.com/kaiosilveira/typescript-value-object)):

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

**C#** ([kaiosilveira/csharp-value-object](https://github.com/kaiosilveira/csharp-value-object)):

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
