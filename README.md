# Spectral Integration With pre-commit.com

In this example you'll see how to use Spectral with [pre-commit](https://pre-commit.com/), a generic Git commit hook manager.

## Usage

We're going to be using the Spectral pre-commit hook that pulls a docker image and runs Spectral from a Spectral docker image.

First, create some file, e.g. `touch foobar`, and then:

```
$ git add .
$ pre-commit run
```

You should get something like:

```
spectral scanner.........................................................Failed
- hook id: spectral
- exit code: 1

/src/secret.txt
0:20 Error Visible AWS Key CLD001

✖ found 1 matches
  scanned 19940 bytes and 23 files in 65ms
```

We've just _simulated_ a commit. If you integrate pre-commit, this should happen every time you try to commit a change.
