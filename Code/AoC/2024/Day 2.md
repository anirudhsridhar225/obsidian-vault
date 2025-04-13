both parts will be in rust

```rust
use std::fs::File;
use std::io::{self, BufRead, BufReader};

fn is_strictly_decreasing(arr: &Vec<i32>) -> bool {
    for i in 0..arr.len() {
        if i == arr.len() - 1 {
            break;
        }
        if arr[i] < arr[i + 1] || !(1..4).contains(&(arr[i] - arr[i+1]).abs()) {
            return false;
        }
    }
    true
}

fn is_strictly_increasing(arr: &Vec<i32>) -> bool {
    for i in 0..arr.len() {
        if i == arr.len() - 1 {
            break;
        }
        if arr[i] > arr[i + 1] || !(1..4).contains(&(arr[i] - arr[i+1]).abs()) {
            return false;
        }
    }
    true
}

fn can_be_made_safe(arr: &Vec<i32>) -> bool {
	if is_strictly_increasing(&arr) || is_strictly_decreasing(&arr) {
		return true;
	}

	for i in 0..arr.len() {
		let mut temp = arr.clone();
		temp.remove(i);
		if is_strictly_decreasing(&temp) || is_strictly_increasing(&temp) {
			return true;
		}
	}
	false
}

fn validate_arrays(ip_array: Vec<Vec<i32>>) -> i32 {
    let mut count: i32 = 0;
    for arr in ip_array {
        if is_strictly_decreasing(&arr) || is_strictly_increasing(&arr) {
            count += 1;
        } else if can_be_made_safe(&arr) {
	        count += 1;
        }
    }
    count
} 

fn main() -> io::Result<()> {

    let file = File::open("day2.txt")?;
    let reader = BufReader::new(file);
    let mut contents: Vec<String> = Vec::new();

    for line in reader.lines() {
        contents.push(line?);
    }

    let mut input_array: Vec<Vec<i32>> = Vec::new();

    for i in &contents {
        let split = i.split_whitespace();
        let mut temp_array: Vec<i32> = Vec::new();
        for j in split {
            temp_array.push(j.parse::<i32>().unwrap());
        }
        input_array.push(temp_array);
    }

    let result = validate_arrays(input_array);
    println!("{}", result);

    Ok(())
}
```
