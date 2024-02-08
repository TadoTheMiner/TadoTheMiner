```rust
use std::fmt;

fn main() {
    let tado = Rustacean{name: "Tadeas", pronouns: &Pronouns::HeHim, distro: "Arch"};
    println!("{tado}");
}

#[allow(dead_code)]
struct Rustacean<'a> {
    name: &'a str,
    pronouns: &'a Pronouns<'a>,
    distro: &'a str,
}

#[allow(dead_code)]
enum Pronouns<'a> {
    HeHim,
    SheHer,
    TheyThem,
    ItIts,
    Other(&'a str),
}

impl fmt::Display for Rustacean<'_> {
    fn fmt(&self, f: &mut fmt::Formatter<'_>) -> fmt::Result {
        write!(f, "Hi! I am {}, and use {} BTW!", self.name, self.distro)
    }
}

```
