# release-plz

[![Crates.io](https://img.shields.io/crates/v/release-plz.svg)](https://crates.io/crates/release-plz)
[![Docs.rs](https://docs.rs/release-plz/badge.svg)](https://docs.rs/release-plz)
[![CI](https://github.com/MarcoIeni/release-plz/workflows/CI/badge.svg)](https://github.com/MarcoIeni/release-plz/actions)

Release-plz updates the versions of your rust packages, by analyzing you git history,
based on [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/).
Release-plz can update your `Cargo.toml` files locally, or by opening a GitHub Pull Request.

Once you update the versions, you can then use a command like
[cargo workspaces](https://crates.io/crates/cargo-workspaces) `publish` to publish the changes.

In this way you can have a fully automated release pipeline.
This means you can easily release changes more frequently, without the fear of doing typo or other
subtle manual mistakes.

## Similar projects

Release-plz is inspired by [release-please](https://github.com/googleapis/release-please),
but instead of determining the next versions based on git tags, release-plz compares local packages with
the ones published in the cargo registry.
Furthermore, release-plz doesn't need any configuration.

## Installation

### Requirements

- git

### Cargo

* Install the rust toolchain in order to have cargo installed by following
  [this](https://www.rust-lang.org/tools/install) guide.
* run `cargo install release-plz`

## Flow

1. Start a repository -> release-plz figures out the repository is not published, so it opens a PR where it doesn't change Cargo.toml, but it changes CHANGELOG based on your commits.
2. After you have published 0.1.0, you do other changes -> release-plz opens a PR with both CHANGELOG and Cargo.toml changes.
3. After you just published something, release-plz will not open PRs, because it sees that local project is the same as crates.io.

## License

Licensed under either of

 * Apache License, Version 2.0
   ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license
   ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

## Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.

See [CONTRIBUTING.md](CONTRIBUTING.md).
