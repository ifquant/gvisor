package(licenses = ["notice"])  # Apache 2.0

load("//tools/go_stateify:defs.bzl", "go_library", "go_test")

go_library(
    name = "ramfs",
    srcs = [
        "dir.go",
        "file.go",
        "ramfs.go",
        "socket.go",
        "symlink.go",
        "tree.go",
    ],
    importpath = "gvisor.googlesource.com/gvisor/pkg/sentry/fs/ramfs",
    visibility = ["//pkg/sentry:internal"],
    deps = [
        "//pkg/secio",
        "//pkg/sentry/context",
        "//pkg/sentry/fs",
        "//pkg/sentry/fs/anon",
        "//pkg/sentry/fs/fsutil",
        "//pkg/sentry/kernel/time",
        "//pkg/sentry/memmap",
        "//pkg/sentry/safemem",
        "//pkg/sentry/socket/unix/transport",
        "//pkg/sentry/usermem",
        "//pkg/syserror",
        "//pkg/waiter",
    ],
)

go_test(
    name = "ramfs_test",
    size = "small",
    srcs = ["tree_test.go"],
    embed = [":ramfs"],
    deps = [
        "//pkg/sentry/context/contexttest",
        "//pkg/sentry/fs",
    ],
)
