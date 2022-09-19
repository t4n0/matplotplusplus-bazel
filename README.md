# About

These instruction will provide a bazel target for [matplot++](https://github.com/alandefreitas/matplotplusplus).

# Integrate

1) Add these lines to your `WORKSPACE` file:

```
load("@bazel_tools//tools/build_defs/repo:git.bzl", "new_git_repository")

new_git_repository(
    name = "matplot",
    branch = "master",
    build_file = "//:BUILD.matplot",
    remote = "https://github.com/alandefreitas/matplotplusplus",
)
```

2) Copy the file `BUILD.matplot` to your workspace root.

# Caveat

- Note that [matplot++](https://github.com/alandefreitas/matplotplusplus) has certain system dependencies (e.g. `gnuplot`).
- Only the `gnuplot` backend from [matplot++](https://github.com/alandefreitas/matplotplusplus) is supported.
- Only the `X11` window system is supported.

# Contribute

Feel free to reach out if you have any suggestions for improvement. Thanks!