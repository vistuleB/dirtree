# dirtree

[![Package Version](https://img.shields.io/hexpm/v/dirtree)](https://hex.pm/packages/dirtree)
[![Hex Docs](https://img.shields.io/badge/hex-docs-ffaff3)](https://hexdocs.pm/dirtree/)

```sh
gleam add dirtree@1
```

A directory tree abstraction including a pretty-printer.

```gleam
import dirtree

pub fn main() -> Nil {
  let tree = dirtree.from_terminals(
    "../examples",
    [
      "futuristic/pngs/png1.png",
      "futuristic/svgs/svg1.png",
      "empty-directory/",
      "notes/README.md",
      "futuristic/pngs/png2.png",
      "notes/old-README.md",
      "futuristic/svgs/svg2.png",
    ],
  )

  tree
  |> dt.pretty_print(1)
  |> string.join("\n")
  |> io.println

  // ->
  //
  // ../examples
  //    ├─ empty-directory
  //    ├─ futuristic
  //    │  ├─ pngs
  //    │  │  ├─ png1.png
  //    │  │  └─ png2.png
  //    │  └─ svgs
  //    │     ├─ svg1.png
  //    │     └─ svg2.png
  //    └─ notes
  //       ├─ README.md
  //       └─ old-README.md
}
```

Further documentation can be found at <https://hexdocs.pm/dirtree>.

## Development

```sh
gleam run   # Run the project
gleam test  # Run the tests
```
