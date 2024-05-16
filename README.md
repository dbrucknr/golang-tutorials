# Installing Golang on Pop_Os!
- [Releases](https://go.dev/dl/)

1. `wget https://go.dev/dl/go1.22.3.linux-amd64.tar.gz`
2. `sudo tar -C /usr/local -xzf go1.22.3.linux-amd64.tar.gz`
3. `nano .bashrc`
    - Add: `export PATH="$PATH:/usr/local/go/bin"` to `.bashrc`
4. Close terminal and start a new one
5. `go version` in terminal
    - Results in: `go version go1.22.3 linux/amd64`

## Tutorials
 - [Tutorial List](https://go.dev/doc/tutorial/)

### Getting Started Tutorial:
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

#### Creating a Module
- [Create a Module](https://go.dev/doc/tutorial/create-module)
- [Call Module Code](https://go.dev/doc/tutorial/call-module-code)
- [Return and handle an error](https://go.dev/doc/tutorial/handle-errors)
- [Random Greeting](https://go.dev/doc/tutorial/random-greeting)
- [Return Greetings for Multiple People](https://go.dev/doc/tutorial/greetings-multiple-people)
- [Add a test](https://go.dev/doc/tutorial/add-a-test)

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