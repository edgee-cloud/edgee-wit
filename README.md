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

This original wit file has no dependencies for now, so the the deps.toml and deps.lock remain empty.

## Releasing
- Update the wit as desired.
- Add and commit
- Tag the version e.g. 'git tag v0.2.3'
- Push the tags 'git push --tags'
- On github.com, draft a new release pointing to this tag
- Copy the url link to the release

Adopting the new version on downstream projects:
- Update the deps.toml file to point to your new release.
- Update the wit/world.wit to match the version
- Run wit-deps in its crate folder
- Resolve any compilation issues
