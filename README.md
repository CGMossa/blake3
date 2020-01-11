
<!-- README.md is generated from README.Rmd. Please edit that file -->

# blake3

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)
<!-- badges: end -->

`blake3` is an interface to the
[BLAKE3](https://github.com/BLAKE3-team/BLAKE3) cryptographic hash
function.

To quote blake3’s readme:

> BLAKE3 is a cryptographic hash function that is:
> 
>   - Much faster than MD5, SHA-1, SHA-2, SHA-3, and BLAKE2.
>   - Secure, unlike MD5 and SHA-1. And secure against length extension,
>     unlike SHA-2.
>   - Highly parallelizable across any number of threads and SIMD lanes,
>     because it’s a Merkle \> tree on the inside.
>   - Capable of verified streaming and incremental updates, again
>     because it’s a Merkle tree.
>   - A PRF, MAC, KDF, and XOF, as well as a regular hash.
>   - One algorithm with no variants, which is fast on x86-64 and also
>     on smaller architectures.

## Installation

``` r
remotes::install_github("dirkschumacher/blake3")
```

Also make sure to have a very recent rust compiler. The best way to
install the rust toolchain is to use [rustup](https://rustup.rs/).

## Example

``` r
library(blake3)

input <- "This is a string"
hash <- blake3_hash_raw(charToRaw(input))
(sodium::bin2hex(hash))
#> [1] "718b749f12a61257438b2ea6643555fd995001c9d9ff84764f93f82610a780f2"
```

## License

MIT
