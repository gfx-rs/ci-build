# ci-build

Automated action for building/hosting components we need in CI

## Mesa

If you push a new tag to this repository, the "Build" action in
[`artifacts.yml`] will fetch the Mesa sources from
`archive.mesa3d.org`, build them from source, and post a new GitHub
release named after the tag. Generally we use tags named `buildN`.

The [`wgpu`] repository's CI and CTS jobs use the [`Install Mesa`]
action to install these releases.

[`artifacts.yml`]: .github/workflows/artifacts.yml
[`wgpu`]: github.com/gfx-rs/wgpu
[`Install Mesa`]: https://github.com/gfx-rs/wgpu/blob/trunk/.github/actions/install-mesa/action.yml
