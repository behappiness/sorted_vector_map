load("@fbcode_macros//build_defs:rust_library.bzl", "rust_library")

oncall("autocargo")

rust_library(
    name = "sorted_vector_map",
    srcs = glob([
        "src/**/*.rs",
        "benches/**/*.rs",
        "README.*",
    ]),
    autocargo = {
        "cargo_toml_config": {
            "bench": [
                {
                    "harness": False,
                    "name": "map",
                },
                {
                    "harness": False,
                    "name": "set",
                },
            ],
            "dependencies_override": {"dev-dependencies": {"minibench": {"version": None}}},
            "extra_buck_dependencies": {
                "dev-dependencies": [
                    "//eden/scm/lib/minibench:minibench",
                ],
            },
            "package": {
                "authors": [
                    "Facebook <opensource+crates-sorted-vector-map@fb.com>",
                ],
                "categories": ["data-structures"],
                "description": "maps and sets backed by sorted vectors",
                "keywords": [
                    "map",
                    "set",
                ],
                "readme": "README.md",
                "repository": "https://github.com/facebookexperimental/rust-shed",
                "version": "0.2.0",
            },
        },
    },
    deps = [
        "fbsource//third-party/rust:itertools",
        "fbsource//third-party/rust:quickcheck",
    ],
)
