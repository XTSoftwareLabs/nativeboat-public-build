# NativeBoat public build

This repository hosts the cloud builds of the NativeBoat platform. Each build
compiles an Electron project from a public GitHub repository into a native
Windows executable with
[NativeBoat Build Action](https://github.com/XTSoftwareLabs/nativeboat-action),
on GitHub-hosted runners.

## How it works

- Builds are started only by the NativeBoat platform, using its own
  credentials. Users of the platform have no access to this repository and
  cannot start workflows here.
- Every build gets its own branch, `runs/<run id>`, created by the platform. The
  branch holds a single generated workflow (`.github/workflows/nativeboat-run.yml`)
  and a `run.json` manifest describing what is built: the source repository,
  the exact commit, and the Electron project path.
- Builds, with their logs and outputs, are deleted automatically when they
  expire (3 days by default), together with their branch.
- `main` contains no workflows.

## Contributions

This repository is operated by the platform; pull requests are not accepted.
Report problems with the compiler in the
[NativeBoat release issues](https://github.com/XTSoftwareLabs/nativeboat-release/issues).
