# textkit

Everyday helpers for text: slugs, title case, camelCase and snake_case, truncating and word wrapping.

دوال يومية للنصوص: تحويل العناوين إلى روابط (slug)، وتكبير أوائل الكلمات، وcamelCase وsnake_case، والاختصار، وتقسيم النص إلى أسطر.

Requires Elomar-Lang 0.2.0 or later.

## Install

```text
elomar add textkit
```

or in `elomar.toml`:

```toml
[dependencies]
textkit = "0.1"
```

## Use

```elomar
use textkit.text

fn main() {
    print(text.slugify("Hello, World!"))          // hello-world
    print(text.slugify("مرحبا بالعالم"))          // مرحبا-بالعالم
    print(text.title_case("the old man"))         // The Old Man
    print(text.camel_case("first-name"))          // firstName
    print(text.truncate("a long sentence", 7))    // a long…
    print(text.wrap("the quick brown fox", 10))   // ["the quick", "brown fox"]
}
```

| Function (`text.…`) | |
|---|---|
| `slugify(s) -> String` | lower case, letters and digits of any script, `-` between words |
| `title_case(s) -> String` | capital first letter for each word |
| `capitalize(s) -> String` | capital first letter |
| `camel_case(s) -> String` | `first-name_here` → `firstNameHere` |
| `snake_case(s) -> String` | `Hello World` → `hello_world` |
| `truncate(s, max) -> String` | at most `max` letters, ending with `…` when cut |
| `wrap(s, width) -> List<String>` | lines of at most `width` letters, broken between words |
| `is_blank(s) -> Bool` | only spaces, or empty |
| `count_words(s) -> Int` | number of words |

## بالعربية

ثبّت الحزمة بالأمر `elomar add textkit`، ثم استوردها بـ `use textkit.text`. الأمثلة
والدوال أعلاه تعمل كما هي، والحزمة تحتاج Elomar-Lang 0.2.0 أو أحدث.

## Development

```text
elomar test
elomar fmt --check .
```

## License

MIT or Apache-2.0, at your option.
