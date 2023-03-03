constraint_value(
    name = "smartcard_embedded_java",
    constraint_setting = "@platforms//os",
)

platform(
  name = "platform",
  constraint_values = [
    ":smartcard_embedded_java",
  ]
)

java_library(
  name = "java_test",
  srcs = ["test.java"]
)
