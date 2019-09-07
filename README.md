# Git IPLD remote helper

Push and fetch commits using IPFS!

This helper is experimental as of now

## Usage
```
Clone an example repository:
$ git clone ipld://2347e110c29742a1783134ef45f5bff58b29e40e

Pull a commit:
$ git pull ipld://2347e110c29742a1783134ef45f5bff58b29e40e

Push:
$ git push --set-upstream ipld:// master
```

Note: Some features like remote tracking are still missing, though the plugin is
quite usable. IPNS helper is WIP and doesn't yet do what it should

## Installation
Make sure you run go-ipfs 0.4.17 or newer as we need git support
1. `go get -u -v github.com/viraja1/git-remote-ipld`
2. `cd ~/go/src/github.com/viraja1/git-remote-ipld`
3. `GO111MODULE=on make`
4. `cd cmd/git-remote-ipld`
5. `GO111MODULE=on go install .`

## Limitations / TODOs
* ipns remote is not implemented fully yet

# Troubleshooting
* `fetch: manifest has unsupported version: 2 (we support 3)` on any command
  - This usually means that tracker data format has changed
  - Simply do `rm -rf .git/ipld`
* `command [...] EOF` or `[...] no parser for format "git" using input type "raw"`
  - You don't have git IPFS plugin properly installed, see step 5 of installation.

## License
MIT
