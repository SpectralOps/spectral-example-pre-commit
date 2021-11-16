# Spectral Integration With pre-commit.com

In this example you'll see how to use Spectral with [pre-commit](https://pre-commit.com/), a generic Git commit hook manager.

## Usage

We're going to be using the Spectral pre-commit hook that runs the Spectral executable locally (assuming you followed [the instructions](https://github.com/SpectralOps/spectral-pre-commit)).

Try this:

```
$ echo "AKIA4HKD3VF23AEA7KWV" > secret.txt
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

If you have a Spectral configuration in your repo (under the `.spectral` dir) you should run pre-commit with the `--all-files` to make sure Spectral uses this configuration with every run.
