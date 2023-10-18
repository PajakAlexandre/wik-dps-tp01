# Rust API
___

## Description
This is a simple API written in Rust. The objective is to create a the `/ping` endpoint that returns a JSON with the header content of the request.
To do this we will use:
- the [Arctix Web](https://actix.rs/) framework.
- the [serde](https://serde.rs/) library for serialization and deserialization.
- the [serde_json](https://docs.serde.rs/serde_json/) library for JSON support.
- the [std](https://doc.rust-lang.org/std/) library for the hashmap and env variables.

## How to run
To run the API you need to have Rust installed. You can install it with [rustup](https://rustup.rs/).

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Activate the Rust environment.

```bash
source "$HOME/.cargo/env"
```

Check the Rust version.

```bash
rustc -V
```

Clone the repository.

```bash
git clone https://gitlab.com/apajak/wik-dps-tp01.git
```

Add dependencies.

```bash
cd rust_api
cargo add actix-web
cargo add serde
cargo add serde_json
```

Run the API.

```bash
cargo run
```
## Environment variables

If you want to change the port of the API you can use the `PING_LISTEN_PORT` environment variable.

```bash
export PING_LISTEN_PORT=8081
```

Instead the default port is `8080`.

## Endpoints

### /ping [GET]

This endpoint returns a JSON with the header content of the request.

```bash
curl -X GET http://localhost:8081/ping
```

```json
{"user-agent":"curl/7.81.0","accept":"*/*","host":"localhost:8081"}
```

## Other endpoints

All the other endpoints return a 404 error with a empty body.

```bash
curl -X GET http://localhost:8081/other
```

```json
{"message":""} 
```