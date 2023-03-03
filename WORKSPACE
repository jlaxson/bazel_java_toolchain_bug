android_ndk_repository(
    name = "androidndk",
    api_level = 26,
)

android_sdk_repository(
    name = "androidsdk",
    api_level = 26,
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "rules_java",
    urls = [
        "https://github.com/bazelbuild/rules_java/releases/download/5.4.1/rules_java-5.4.1.tar.gz",
    ],
    sha256 = "a1f82b730b9c6395d3653032bd7e3a660f9d5ddb1099f427c1e1fe768f92e395",
)
load("@rules_java//java:repositories.bzl", "rules_java_dependencies", "rules_java_toolchains")
rules_java_dependencies()
rules_java_toolchains()
