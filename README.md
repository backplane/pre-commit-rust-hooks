# pre-commit hooks for Rust

[Rust](https://www.rust-lang.org) hooks for [pre-commit](https://pre-commit.com).

This repo was inspired by the pre-commit hooks found in [`doublify/pre-commit-rust`](https://github.com/doublify/pre-commit-rust) on 20-Mar-2023.

The code here is released with the [`0BSD`](https://opensource.org/license/0bsd/) license.

## Using the hooks

Add the following entry to your `.pre-commit.yml`

```yaml
-   repo: https://github.com/backplane/pre-commit-rust-hooks
    rev: v1.0.1
    hooks:
    -   id: fmt
    -   id: check
    -   id: clippy
    -   id: test
```

Note: The id `fmt-check` is also available if you don't want automatic changes.

## Passing arguments:

If you pass an `args` list to a hook that receives filename arguments you should end that list with the `--` terminator (see below).

* The `fmt` and `fmt-check` hooks receive a list of filenames at the end of their arguments.
* The `check`, `clippy`, and `test` hooks do not receive a list of filenames as arguments.

```yaml
-   repo: https://github.com/backplane/pre-commit-rust-hooks
    rev: v1.0.1
    hooks:
    -   id: fmt
        args: ['--verbose', '--edition', '2018', '--']
```
