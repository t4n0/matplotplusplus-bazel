cc_library(
    name = "matplot",
    deps = ["@matplot_impl"],
)

cc_binary(
    name = "example",
    srcs = ["example.cpp"],
    copts = ["-std=c++17"],
    deps = [":matplot"],
)
