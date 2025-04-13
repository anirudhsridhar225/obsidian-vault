did it in golang for the sillies

```go
package main

import (

    "fmt"
    "os"
    "regexp"
    "strconv"
    "strings"
    
)

func ReadFile() string {
    fmt.Println("Reading file")
    fileName := "day3.txt"
    data, err := os.ReadFile(fileName)
    if err != nil {
        panic(err)
    }
    ip_array := string(data)
    return ip_array
}

func compute(data string) int {
    result := 0
    re := regexp.MustCompile(`mul\(\d+,\d+\)`)
    match := re.FindAllString(data, -1)

    for _, v := range match {
        altRe := regexp.MustCompile(`mul\((\d+),(\d+)\)`)
        submatch := altRe.FindStringSubmatch(v)
        num1, _ := strconv.Atoi(submatch[1])
        num2, _ := strconv.Atoi(submatch[2])
        result += num1 * num2
    }

    return result
}

func AltCompute(data string) int {
    result := 0
    enabled := true

    re := regexp.MustCompile(`(do\(\)|don't\(\)|mul\(\d+,\d+\))`)
    matches := re.FindAllString(data, -1)

    for _, v := range matches {
        if v == "do()" {
            enabled = true
        } else if v == "don't()" {
            enabled = false
        } else if strings.HasPrefix(v, "mul(") && enabled {
            reMul := regexp.MustCompile(`mul\((\d+),(\d+)\)`)
            submatch := reMul.FindStringSubmatch(v)
            num1, _ := strconv.Atoi(submatch[1])
            num2, _ := strconv.Atoi(submatch[2])
            result += num1 * num2
        }
    }

    return result
}

func main() {
    data := ReadFile()

    result := compute(data)
    altResult := AltCompute(data)

    fmt.Println(result)
    fmt.Println(altResult)
}
```
