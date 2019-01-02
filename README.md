# Wrappers for C/C++ rules

Status: This is **ALPHA** software.

## Rules

* [cc_binary](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_binary)
* [cc_import](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_import)
* [cc_library](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_library)
* [cc_proto_library](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_proto_library)
* [cc_test](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_test)
* [fdo_prefetch_hints](https://docs.bazel.build/versions/master/be/c-cpp.html#fdo_prefetch_hints)
* [fdo_profile](https://docs.bazel.build/versions/master/be/c-cpp.html#fdo_profile)

## Overview

This repository contains simple wrappers around
[the native C/C++ rules provided by Bazel](https://docs.bazel.build/versions/master/be/c-cpp.html#cc_binary).
Using them provides no functional gain over the built-in rules, except
that it permits users to substitute the implementation by other
(Starlark-based) rules.

## Setup

```python
git_repository(
    name = "io_bazel_rules_cc",
    remote = "https://github.com/bazelbuild/rules_cc.git",
    # NOT VALID!  Replace this with a Git commit SHA.
    commit = "{HEAD}",
)
```

Then in your `BUILD` files load the C/C++ rules with:

``` python
load(
  "@io_bazel_rules_cc//cc:cc.bzl",
  "cc_binary", "cc_library", "cc_test",
)

cc_binary(
  name = "main",
  ...
)
```
