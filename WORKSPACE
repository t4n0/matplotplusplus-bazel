load("@bazel_tools//tools/build_defs/repo:git.bzl", "new_git_repository")

BUILD_MATPLOT = """

cc_library(
    name = "cimg",
    hdrs = ["source/3rd_party/cimg/CImg.h"],
    copts = [
        "-std=c++17",
        "-w",
    ],
    strip_include_prefix = "source/3rd_party/cimg",
)

cc_library(
    name = "nodesoup",
    srcs = glob([
        "source/3rd_party/nodesoup/**/*.cpp",
        "source/3rd_party/nodesoup/**/*.hpp",
    ]),
    hdrs = ["source/3rd_party/nodesoup/include/nodesoup.hpp"],
    copts = [
        "-std=c++17",
        "-w",
    ],
    strip_include_prefix = "source/3rd_party/nodesoup/include/",
)

cc_library(
    name = "matplot_impl",
    srcs = glob(
        include = ["source/matplot/**/*.cpp"],
        exclude = ["**/*opengl*"],
    ),
    hdrs = glob(
        include = ["source/matplot/**/*.h"],
        exclude = ["**/*opengl*"],
    ),
    copts = [
        "-std=c++17",
        "-w",
    ],
    linkopts = ["-lX11"],
    strip_include_prefix = "source",
    visibility = ["//visibility:public"],
    deps = [
        ":cimg",
        ":nodesoup",
    ],
)

"""

new_git_repository(
    name = "matplot_impl",
    branch = "master",
    build_file_content = BUILD_MATPLOT,
    remote = "https://github.com/alandefreitas/matplotplusplus",
)
