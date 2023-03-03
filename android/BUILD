java_library(
  name = "java_test",
  srcs = ["test.java"]
)

android_binary(
  name = "foo",
  deps = [":java_test"],
  manifest = "manifest.xml",
  custom_package = "testme"
)

platform(
  name = "android",
  constraint_values = [
    "@platforms//os:android",
    "@platforms//cpu:aarch64"
  ]
)
