## :warning: Known Issues

- No binaries yet (you can download artifacts from each commit/PR tests)
- **App won't ever be sandboxed, hardened, notarized or signed**. 
  - If you don't trust the binaries please build from source. You still need to convince Apple you want to run the binary you just built.

## Installation

1. Download [not yet available] 7z,
2. Uncompress the [not yet available] 7z file using Keka or The Unarchiver.
3. Move the application somewhere outside ~/Downloads
4. Do whatever Apple requires to run your own, unsigned code
5. Execute the application by double clicking on its icon

## CLI interface

If you want to access koreader using the commandline don't do a symlink. Just export the PATH.

For example: for `/Applications/KOReader.app` do `export PATH=$PATH:/Applications/KOReader.app/Contents/MacOS`

