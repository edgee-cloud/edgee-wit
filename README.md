In the WASM community there is some tooling for it: wit-deps.

Wit-deps is a dependency tool, native to wasm. It expects a 'deps.toml' file in the wit folder, listing url's to dependent wit archives.

Example contents of a deps.toml file:

```toml
io = "https://github.com/WebAssembly/wasi-io/archive/main.tar.gz"
```

In this case there is a dependency called 'io' pointing to a tgz of the wasi-io

To use wit-deps, install it first:

```bash
cargo install wit-deps-cli
```
Run it:

```bash
wit-deps
```

That should download and unpack all dependencies into the wit/deps/ folder

So first we will need to create such an artifact from our protocols.wit

Second we should create dependencies to it, and remove the wit files from all other repo;s
