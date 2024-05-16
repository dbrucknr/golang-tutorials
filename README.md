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