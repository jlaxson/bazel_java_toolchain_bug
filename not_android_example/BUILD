# load("@rules_java//java:defs.bzl", "java_library")

constraint_value(
    name = "smartcard_embedded_java",
    constraint_setting = "@platforms//os",
)

platform(
    name = "platform",
    constraint_values = [
        ":smartcard_embedded_java",
    ],
)

java_library(
    name = "java_lib",
    srcs = ["Test.java"],
)

java_binary(
    name = "java_bin",
    srcs = ["Test.java"],
)

java_test(
    name = "java_test",
    srcs = ["Test.java"],
    test_class = "hello.Test",
)

platform(
    name = "linux",
    constraint_values = [
        "@platforms//os:linux",
        "@platforms//cpu:x86_64",
    ],
)
