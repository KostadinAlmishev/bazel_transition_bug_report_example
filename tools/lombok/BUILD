load("@rules_java//java:defs.bzl", "java_library", "java_plugin")
load("@rules_jvm_external//:defs.bzl", "artifact")

java_plugin(
    name = "lombok_plugin",
    generates_api = True,
    processor_class = "lombok.launch.AnnotationProcessorHider$AnnotationProcessor",
    deps = [
        artifact("org.projectlombok:lombok"),
    ],
)

java_library(
    name = "lombok",
    exported_plugins = [
        ":lombok_plugin",
    ],
    neverlink = True,
    visibility = ["//visibility:public"],
    exports = [
        "@maven//:org_projectlombok_lombok",
    ],
)
