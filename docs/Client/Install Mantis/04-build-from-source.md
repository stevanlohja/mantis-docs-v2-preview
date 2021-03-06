# Build from Source

We recommend using the [client's pre-built binaries from our releases](https://github.com/input-output-hk/mantis/releases) for most users.
You can build the Mantis client from source as an alternative to its downloading. And You can do so using [SBT](#sbt) or [Nix](#nix).

## SBT

### Requirements to build with SBT
- JDK 1.8 (download from java.com)
- SBT (download sbt)
- Python 2.7.15 (download from python.org)

### Build the client

1. To build the client, first, download the repository and cd into the root directory:

```
git clone git@github.com:input-output-hk/mantis.git
cd mantis
```

2. Use sbt to create the client's distribution:

```
git submodule update --recursive --init
sbt dist
```

This updates all submodules and creates a distribution zip in `.<mantis-install-folder>/target/universal/`.

As an alternative to building with SBT, you can use Nix.

## Nix

### Requirements to build with Nix

- Nix (Install instructions on https://github.com/NixOS/nix#installation)
- To load environment variables, run `/home/<user>/.nix-profile/etc/profile.d/nix.sh`

### Build the client

1. To build the client, first, use the `nix-build` command, which will build project files:

```
nix-build
```

2. Then, regenerate lock files:

```
Nix-shell
sbtix-gen-all2
```

### What to do in case of failure

If Nix build fails during the "ensure Nix expressions are up-to-date" step, check the artifacts of that step. There should be a patch provided, which you can apply locally with:
`patch -p1 < downloaded.patch`

This patch will update the lock files for you.

### Why so many lock files?

- repo.nix : this file is generated by the sbtix-gen command and includes only the build dependencies for the project.
- project/repo.nix : this file is generated by the sbtix-gen-all command, includes only the plugin dependencies, and also generates repo.nix.
- project/project/repo.nix : this file is generated by the sbtix-gen-all2 command and includes only the plugin dependencies. It also generates repo.nix and project/repo.nix.

### Getting an error: unsupported argument 'submodules' to 'fetchGit'

To resolve this issue, please make sure to update your version of Nix. fetchGit support for submodules is relatively recent.

Update the version of Nix you are using, otherwise:
- Remove the "submodules = true;" argument from fetchGit (in `./nix/pkgs/mantis/default.nix`).
- git submodule update --recursive --init
- nix-build


## Mantis wallet from source

We recommend using the [pre-built binaries](https://github.com/input-output-hk/mantis-wallet/releases) in releases for most users.
The following are the instructions to build the Mantis wallet from source.

### Requirements

- Node.js - v12+ (optional nvm)
- yarn - tested with 1.21.1-1.22.5

### Cloning and Initializing the project

To clone and initialize your project, run the following command:

```
git clone git@github.com:input-output-hk/mantis-wallet.git
cd mantis-wallet
```

Running the yarn command in the project directory will download the dependencies.

```
yarn
```

Build the app to the build folder.
```
yarn build-renderer
yarn build-main
```

`yarn build-renderer` and `yarn build-main` followed by `yarn electron` will open the production version of the Electron application.
```
yarn electron
```

For distribution files, build the storybook, followed by the distribution build:

`yarn build-storybook` creates the static storybook build in the `storybook-static` folder.
```
yarn build-storybook
```

Now build your appropriate package, depending on your operating system:
```
yarn build-dist # for Linux of macOS
# or
yarn build-dist-win # for Windows
```

Builds the main process code to the build/main directory. It's required to be run before running electron-dev or electron

```
	yarn electron-dev
```

yarn electron-dev will open the Electron application in debug mode.

```
	yarn electron
```

If you are looking for the developer build, follow the process documented in the [wallet README](https://github.com/input-output-hk/mantis-wallet#scripts-for-development) for more details.