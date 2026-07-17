# ci-build

Automated action for building/hosting components we need in CI

## Mesa

If you push a new tag to this repository, the "Build" action in
[`artifacts.yml`] will fetch the Mesa sources from `archive.mesa3d.org`, build
them from source, and post a new GitHub release named after the tag. Generally
we use tags named `buildN`.

The [`wgpu`] repository's CI and CTS jobs use the [`Install Mesa`] action to
install these releases on Linux. On Windows, that action fetches a prebuilt
release from [`pall1000/mesa-dist-win`]. Both Linux and Windows try to install
the same version of Mesa, so make sure that the version you build here for Linux
is also available from `pal1000`; it is sometimes a few minor revisions behind
`archive.mesa3d.org`. Consider matching the Mesa currently packaged with Ubuntu;
this may help `wgpu`'s CI behave more like developers' machines.

[`artifacts.yml`]: .github/workflows/artifacts.yml
[`wgpu`]: github.com/gfx-rs/wgpu
[`Install Mesa`]: https://github.com/gfx-rs/wgpu/blob/trunk/.github/actions/install-mesa/action.yml
[`pal1000/mesa-dist-win`]: https://github.com/pal1000/mesa-dist-win/releases
