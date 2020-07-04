load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

##
## Binaries
##
go_binary(
    name = "hrelayd",
    srcs = ["hrelayd.go"],
    pure = "on",
    deps = [
        "//:hrelay",
        "//proto:hrelayd_go_proto",
        "@com_github_golang_protobuf//proto:go_default_library",
        "@org_golang_x_crypto//acme:go_default_library",
        "@org_golang_x_crypto//acme/autocert:go_default_library",
    ],
)

##
## Libraries
##
go_library(
    name = "hrelay",
    srcs = [
        "client.go",
        "server.go",
        "util.go",
    ],
    importpath = "github.com/BranLwyd/hrelay/hrelay",
    visibility = ["//visibility:public"],
    deps = [
        "//proto:hrelay_go_proto",
        "@com_github_golang_protobuf//proto:go_default_library",
    ],
)

go_test(
    name = "hrelay_test",
    timeout = "short",
    srcs = ["hrelay_test.go"],
    embed = [":hrelay"],
)
