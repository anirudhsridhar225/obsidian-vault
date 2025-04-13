just use the os module lmao

```go
package main

import (
	"fmt"
	"os"
)

func WriteFile() {
	fmt.Println("Writing file")
	file, err := os.Create("test.txt")

	if (err != nil) {
		panic(err)
	}

	length, err := file.WriteString("welcome to golang hello there")

	if (err != nil) {
		panic(err)
	}
	fmt.Println("filename: " + file.Name())
	fmt.Println("filesize:", length)
}

func ReadFile() {
    fmt.Println("Reading file")
    fileName := "day3.txt"
    data, err := os.ReadFile(fileName)

    if err != nil {
        panic(err)
    }
    
    fmt.Println("filename: " + fileName)
    fmt.Println("file size:", len(data))
}
```