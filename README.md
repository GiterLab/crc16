
# crc16

Go implementation of CRC-16 calculation for majority of widely-used polynomials.</br>
It implements the golang hash.Hash interface.

## Usage

```go
package main

import (
    "fmt"

    "github.com/GiterLab/crc16"
)

func main() {
    table := crc16.MakeTable(crc16.CRC16_MODBUS)

    crc := crc16.Checksum([]byte("Hello world!"), table)
    fmt.Printf("CRC-16 MODBUS: %X\n", crc)

    // using the standard library hash.Hash interface
    h := crc16.New(table)
    h.Write([]byte("Hello world!"))
    fmt.Printf("CRC-16 MODBUS: %X\n", h.Sum16())
}
```
