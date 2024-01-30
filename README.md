# Preview

![image](https://github.com/emesare/sleek/assets/35282038/bdbdcefc-78e1-4bda-9257-bcb7dacada58)


# Usage

Add `sleek` as build dependency to your `Cargo.toml`:

```toml
[dependencies]
slint = "0.3.1"

[build-dependencies]
slint-build = "0.3.1"
sleek = { ... }
```

Call `sleek::generate_import()` from your `build.rs` file. It will generate an import file `../$MY_PROJECT_PATH/ui/_imports/sleek.slint`:

```rust
fn main() {
    sleek::generate_import().unwrap();
    slint_build::compile("ui/my_app.slint").unwrap();
}
```

Add an import to your slint file:

```sleek
import { Button } from "_imports/sleek.slint";

export MyApp := Window {
    preferred-width: 600px;
    preferred-height: 400px;
    title: "MyApp";

    Button {
        text: "Click me";
    }
}
```
