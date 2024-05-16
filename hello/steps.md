# Getting Started Tutorial:
- [Tutorial](https://go.dev/doc/tutorial/getting-started)

1. `mkdir hello && cd hello`
2. `go mod init example/hello`
3. `touch hello.go`
4. Paste:
``` 
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```
5. `go run .`
6. Add module requirement: `import "rsc.io/quote"`
7. Add: `fmt.Println(quote.Go())` into `hello.go`
8. `go mod tidy`