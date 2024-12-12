load("@rules_java//java:java_library.bzl", "java_library")
load("@rules_java//java:java_binary.bzl", "java_binary")
load("//tools/lombok:transition.bzl", "java_rule_without_header_compilation")

java_library(
    name = "lib_with_lombok",
    srcs = glob(["A.java"]),
    deps = [
        "//tools/lombok",
    ],
)

java_rule_without_header_compilation(
    name = "lib_with_lombok_without_header",
    dep = ":lib_with_lombok",
)

java_binary(
    name = "binary",
    srcs = glob(["B.java"]),
    main_class = "example.B",
    deps = [
        ":lib_with_lombok_without_header",
    ],
)
