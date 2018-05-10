package(default_visibility = ["//visibility:public"])

load("@build_bazel_rules_typescript//:defs.bzl", "ts_library")
load("@build_bazel_rules_nodejs//:defs.bzl", "npm_package")

ts_library(
    name = "schematics",
    srcs = glob(
        [
            "**/src/**/*.ts",
        ],
        exclude = [
            "**/src/**/*.spec.ts",
            "**/src/**/files/**/*",
        ],
    ),
    module_name = "@ngrx/schematics",
    tsconfig = ":tsconfig-build.json",
)

npm_package(
    name = "npm_package",
    srcs = [
        ":collection.json",
        ":package.json",
        ":README.md",
    ] + glob([
        "**/src/*/files/**/*",
        "**/schema.json",
        "**/migration.json",
    ]),
    deps = [
        ":schematics",
    ],
)