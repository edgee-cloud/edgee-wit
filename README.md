# Edgee WIT definitions

This repository defines all WIT definitions for Edgee components.

## How to use

Add this to your `wit/deps.toml` file:

```toml
edgee = "https://github.com/edgee-cloud/edgee-wit/archive/refs/tags/v1.0.0.tar.gz"
```

And your `wit/world.wit` file:

```
package edgee:native;

world data-collection {
  export edgee:components/data-collection;
}
```

## Requirements

You need to install `wit-deps`:

```bash
cargo install wit-deps-cli
```

And then run it to install all WIT dependencies:

```bash
wit-deps
```

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
