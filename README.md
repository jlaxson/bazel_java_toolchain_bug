Setup: ensure ANDROID_HOME is set to your sdk path (or remove it from WORKSPACE for the not-android example)
# Android Example

To test: `bazel build --config=android //android/...`, see that it's broken:
```
ERROR: java_android_bazel_test/BUILD:6:15: While resolving toolchains for target //:foo: No matching toolchains found for types @bazel_tools//tools/jdk:runtime_toolchain_type.
```

Works if you remove either `--platforms` or `--java_runtime_version` from .bazelrc, or if you change .bazelversion to something before 6.0 like 5.1.1

# Not Android Example

To Test:

bazel build --config=not_android //not_android_example/...
```
ERROR: <output_base>/external/bazel_tools/tools/jdk/BUILD:28:19: While resolving toolchains for target @bazel_tools//tools/jdk:current_java_runtime: No matching toolchains found for types @bazel_tools//tools/jdk:runtime_toolchain_type.
To debug, rerun with --toolchain_resolution_debug='@bazel_tools//tools/jdk:runtime_toolchain_type'
If platforms or toolchains are a new concept for you, we'd encourage reading https://bazel.build/concepts/platforms-intro.
ERROR: Analysis of target '//not_android_example:java_test' failed; build aborted:
```

# Less esoteric platform example

Assuming you're running on darwin (otherwise change //not_android_example:platform to some other platform)

`bazel test --platforms=//not_android_example //not_android_example:java_test`

`/sandbox/darwin-sandbox/8/execroot/__main__/bazel-out/darwin_arm64-fastbuild/bin/not_android_example/java_test.runfiles/__main__/not_android_example/java_test: line 390: /Volumes/Bazel/8cf025f840017803cd993c3d9e7b9a10/sandbox/darwin-sandbox/8/execroot/__main__/bazel-out/darwin_arm64-fastbuild/bin/not_android_example/java_test.runfiles/remotejdk11_linux/bin/java: cannot execute binary file
`

It's running the wrong jdk for the tests.
