---
title: Random numbers
sidebar:
  order: 11
  label: 2.11 Random numbers
---

## Context

Go provides random number generation in the `math/rand` package. For cryptographic randomness, use `crypto/rand`.

Important functions:

- `rand.Intn(n)` – random integer in `[0, n)`
- `rand.Int()` – random non‑negative integer
- `rand.Float64()` – random float in `[0.0, 1.0)`
- `rand.Seed(seed)` – initialize the generator (deprecated in Go 1.20+; now automatic)

Since Go 1.20, the global random generator is seeded automatically at program start.

## Example

Generate random numbers.

## Code example

```go
package main

import (
    "fmt"
    "math/rand"
    "time"
)

func main() {
    // Random integer between 0 and 99
    fmt.Println("Random int 0-99:", rand.Intn(100))

    // Random float between 0.0 and 1.0
    fmt.Println("Random float:", rand.Float64())

    // Random integer (non-negative)
    fmt.Println("Random int:", rand.Int())

    // For different sequences each run, we can still seed manually (though not required)
    rand.NewSource(time.Now().UnixNano())
    fmt.Println("Seeded random:", rand.Intn(100))
}
```

## Output (example, will vary)

```bash
Random int 0-99: 42
Random float: 0.123456789
Random int: 1234567890123456789
Seeded random: 87
```

## Useful links

- [math/rand package documentation](https://pkg.go.dev/math/rand)
- [Go by Example: Random Numbers](https://gobyexample.com/random-numbers)
