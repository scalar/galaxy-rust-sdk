# Scalar Galaxy

The Scalar Galaxy is an example OpenAPI document to test OpenAPI tools and libraries. It's a fictional universe with fictional planets and fictional data. Get all the data for [all planets](#tag/planets/get/planets).

## Resources

* https://github.com/scalar/scalar
* https://github.com/OAI/OpenAPI-Specification
* https://scalar.com

## Markdown Support

All descriptions *can* contain ~~tons of text~~ **Markdown**. [If GitHub supports the syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax), chances are we're supporting it, too. You can even create [internal links to reference endpoints](#tag/authentication/post/user/signup).

<details>
  <summary>Examples</summary>

  **Blockquotes**

  > I love OpenAPI. <3

  **Tables**

  | Feature          | Availability |
  | ---------------- | ------------ |
  | Markdown Support | ✓            |

  **Accordion**

  ```html
  <details>
    <summary>Using Details Tags</summary>
    <p>HTML Example</p>
  </details>
  ```

  **Images**

  Yes, there's support for images, too!

  ![Empty placeholder image showing the width/height](https://images.placeholders.dev/?width=1280&height=720)

  **Alerts**

  > [!tip]
  > You can now use markdown alerts in your descriptions.

</details>


## Installation

```toml
[dependencies]
scalargalaxy-rust = "0.1.1"
tokio = { version = "1", features = ["full"] }
```

## Usage

The client is asynchronous and built on `tokio` + `reqwest`. Construct it
with the builder, or read credentials from the environment:

```rust,no_run
use scalargalaxy_rust::ScalarGalaxyClient;

async fn run() -> Result<(), Box<dyn std::error::Error>> {
    let client = ScalarGalaxyClient::builder()
        .bearer_token("…")
        .username("…")
        .password("…")
        .api_key_header("…")
        .api_key_query("…")
        .api_key_cookie("…")
        .access_token("…")
        .build()?;

    // Or, reading credentials from the environment:
    let client = ScalarGalaxyClient::from_env()?;
    let _ = client;
    Ok(())
}
```

Every operation returns a request builder; set optional parameters fluently
and finish with `.send().await`:

```rust,ignore
let response = client.planets().list_all_data().send().await?;
```

## Authentication

Credentials can be set on the builder or read from the environment by
`from_env`:

- `bearer_token` — environment variable `SCALAR_BEARER_TOKEN`
- `username` — environment variable `SCALAR_USERNAME`
- `password` — environment variable `SCALAR_PASSWORD`
- `api_key_header` — environment variable `SCALAR_API_KEY_HEADER`
- `api_key_query` — environment variable `SCALAR_API_KEY_QUERY`
- `api_key_cookie` — environment variable `SCALAR_API_KEY_COOKIE`
- `access_token` — environment variable `SCALAR_ACCESS_TOKEN`

## Error handling

Fallible operations return [`scalargalaxy_rust::Error`]. Match on the
result of `send().await` to distinguish API errors (with status and decoded
body) from transport and decoding failures:

```rust,ignore
use scalargalaxy_rust::Error;

match result {
    Ok(value) => { /* … */ }
    Err(Error::Api(api)) => eprintln!("status {}: {:?}", api.status, api.body),
    Err(other) => eprintln!("request failed: {other}"),
}
```

## API reference

See [`api.md`](./api.md) for the full list of resources and operations.


## Contributions

This SDK is generated programmatically. Manual edits to generated files will be
overwritten on the next build.

### SDK created by [Scalar](https://www.scalar.com/?utm_source=demo-api-scalar-galaxy-rust&utm_campaign=sdk)
