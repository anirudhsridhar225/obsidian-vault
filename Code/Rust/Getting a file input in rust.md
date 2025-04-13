
```rust
use std::fs::File;

use std::io::{self, BufRead, BufReader};

  

fn main() -> io::Result<()> {

    let file = File::open("day2.txt")?;

    let reader = BufReader::new(file);

    let mut contents: Vec<String> = Vec::new();

  

    for line in reader.lines() {

        contents.push(line?);

    }

  

    if !contents.is_empty() {

        println!("{}", contents[0]);

    }

  

    Ok(())

}
```
