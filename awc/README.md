# `awc` (Actix Web Client)

> Async HTTP and WebSocket client library.

<!-- prettier-ignore-start -->

[![crates.io](https://img.shields.io/crates/v/awc?label=latest)](https://crates.io/crates/awc)
[![Documentation](https://docs.rs/awc/badge.svg?version=3.3.0)](https://docs.rs/awc/3.3.0)
![MIT or Apache 2.0 licensed](https://img.shields.io/crates/l/awc)
[![Dependency Status](https://deps.rs/crate/awc/3.3.0/status.svg)](https://deps.rs/crate/awc/3.3.0)
[![Chat on Discord](https://img.shields.io/discord/771444961383153695?label=chat&logo=discord)](https://discord.gg/NWpN5mmg3x)

<!-- prettier-ignore-end -->

## Documentation & Resources

- [API Documentation](https://docs.rs/awc)
- [Example Project](https://github.com/actix/examples/tree/master/https-tls/awc-https)
- Minimum Supported Rust Version (MSRV): 1.68

## Example

```rust
use actix_rt::System;
use awc::Client;

fn main() {
    System::new().block_on(async {
        let client = Client::default();

        let res = client
            .get("http://www.rust-lang.org")    // <- Create request builder
            .insert_header(("User-Agent", "Actix-web"))
            .send()                             // <- Send http request
            .await;

        println!("Response: {:?}", res);        // <- server http response
    });
}
```
