# Creating a Module
- [Tutorial](https://go.dev/doc/tutorial/create-module)

1. `mkdir greetings && cd greetings`
2. `go mod init example.com/greetings`
3. `touch greetings.go`
4. Copy in `greetings.go`:
```
package greetings

import "fmt"

// Hello returns a greeting for the named person.
func Hello(name string) string {
    // Return a greeting that embeds the name in a message.
    message := fmt.Sprintf("Hi, %v. Welcome!", name)
    return message
}
```
5. `cd ..`
6. `mkdir helloDependencies && cd helloDependencies`
7. `go mod init example.com/helloDependencies`
8. `touch helloDependencies.go`
9. Copy in `helloDependencies.go`
```
package main

import (
    "fmt"

    "example.com/greetings"
)

func main() {
    // Get a greeting message and print it.
    message := greetings.Hello("Gladys")
    fmt.Println(message)
}
```
10. Edit the example.com/hello module to use your local example.com/greetings module:
    - `go mod edit -replace example.com/greetings=../greetings`
11. `go mod tidy`
12. `go run .`