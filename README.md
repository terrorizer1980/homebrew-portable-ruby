# Homebrew Portable Ruby

Formulae and tools to build versions of Ruby that can be installed and run from anywhere on the filesystem.

## How do I install these formulae

Just `brew install homebrew/portable-ruby/<formula>`.

## How do I build packages for these formulae

### macOS

Run `brew portable-package ruby` inside an OS X 10.10 VM (so it is compatible with all working Homebrew macOS versions).

### Linux

Build a Docker image for your architecture by running:

- `docker build -f Dockerfile --platform linux/amd64 --build-arg img=debian/eol:wheezy -t homebrew-portable .`

Build the `portable-ruby` package using that Docker image.

```sh
docker run --name=homebrew-portable-ruby -w /bottle homebrew-portable brew portable-package ruby
docker cp homebrew-portable-ruby:/bottle .
```

## Current Status

Used in production for Homebrew/brew.

## License

Code is under the [BSD 2 Clause (NetBSD) license](https://github.com/Homebrew/homebrew-portable-ruby/blob/master/LICENSE.txt).
