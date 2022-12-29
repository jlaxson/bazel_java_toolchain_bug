Setup: ensure ANDROID_HOME is set to your sdk path

To test: `bazel build //libs/...`, see that it's broken:
```
ERROR: java_android_bazel_test/BUILD:6:15: While resolving toolchains for target //:foo: No matching toolchains found for types @bazel_tools//tools/jdk:runtime_toolchain_type.
```

Works if you remove either `--platforms` or `--java_runtime_version` from .bazelrc, or if you change .bazelversion to something before 6.0 like 5.1.1
