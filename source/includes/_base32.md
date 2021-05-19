# Base32

**Voken flavored Base32** encoding/decoding, **with auto checksum.**

### Functions

Name             | Params   | Returns
---------------- | -------- | -----------------
Encode           | `[]byte` | `[]byte`
EncodeToString   | `[]byte` | `string`
EncodeFromString | `string` | `[]byte`
EncodeString     | `string` | `string`
Decode           | `[]byte` | `[]byte`, `error`
DecodeToString   | `[]byte` | `string`, `error`
DecodeFromString | `string` | `[]byte`, `error`
DecodeString     | `string` | `string`, `error`
IsBase32String   | `string` | `bool`


## Download and Import

```shell
$ go get -u github.com/voken1000g/go-base32
```


## Import

### Supported languages

- GoLang


## Encode/Decode

```go
package main

import (
    "fmt"
    base32 "github.com/voken1000g/go-base32"
)

func main() {
    input := []byte("Decentralize the Internet")
    encoded := base32.Encode(input)
    decoded, _ := base32.Decode(encoded)

    fmt.Println("encoded (string):", string(encoded))
    fmt.Println("decoded (string):", string(decoded))
}
```

> Output:

```text
encoded (string): 8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6Vsbm
decoded (string): Decentralize the Internet
```

Function         | Params   | Returns
---------------- | -------- | -----------------
Encode           | `[]byte` | `[]byte`
Decode           | `[]byte` | `[]byte`, `error`


## EncodeToString/DecodeToString

```go
package main

import (
    "fmt"
    base32 "github.com/voken1000g/go-base32"
)

func main() {
    input := []byte("Decentralize the Internet")
    encoded := base32.EncodeToString(input)
    decoded, _ := base32.DecodeToString([]byte(encoded))

    fmt.Println("encoded:", encoded)
    fmt.Println("decoded:", decoded)
}
```

> Output:

```text
encoded: 8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6Vsbm
decoded: Decentralize the Internet
```

Function         | Params   | Returns
---------------- | -------- | -----------------
EncodeToString   | `[]byte` | `string`
DecodeToString   | `[]byte` | `string`, `error`



## EncodeFromString/DecodeFromString

```go
package main

import (
    "fmt"
    base32 "github.com/voken1000g/go-base32"
)

func main() {
    input := "Decentralize the Internet"
    encoded := base32.EncodeFromString(input)
    decoded, _ := base32.DecodeFromString(string(encoded))

    fmt.Println("encoded (string):", string(encoded))
    fmt.Println("decoded (string):", string(decoded))
}
```

> Output:

```text
encoded (string): 8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6Vsbm
decoded (string): Decentralize the Internet
```

Function         | Params   | Returns
---------------- | -------- | -----------------
EncodeFromString | `string` | `[]byte`
DecodeFromString | `string` | `[]byte`, `error`



## EncodeString/DecodeString

```go
package main

import (
    "fmt"
    base32 "github.com/voken1000g/go-base32"
)

func main() {
    input := "Decentralize the Internet"
    encoded := base32.EncodeString(input)
    decoded, _ := base32.DecodeString(encoded)

    fmt.Println("encoded:", encoded)
    fmt.Println("decoded:", decoded)
}
```

> Output:

```text
encoded: 8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6Vsbm
decoded: Decentralize the Internet
```

Function         | Params   | Returns
---------------- | -------- | -----------------
EncodeString     | `string` | `string`
DecodeString     | `string` | `string`, `error`



## IsBase32String

```go
package main

import (
    "fmt"
    base32 "github.com/voken1000g/go-base32"
)

func main() {
    input1 := "8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6Vsbm"
    input2 := "8hJP6sbeeHS62u39f9jJ0W38cMG4juKMcnS6VsbM"

    output1 := base32.IsBase32String(input1)
    output2 := base32.IsBase32String(input2)

    fmt.Println("output1:", output1)
    fmt.Println("output2:", output2)
}
```

> Output:

```text
output1: true
output2: false
```

Function         | Params   | Returns
---------------- | -------- | -----------------
IsBase32String   | `string` | `bool`
