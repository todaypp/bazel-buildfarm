config_setting(
    name = "fuse",
    values = {"define": "fuse=true"},
)

java_test(
    name = "tests",
    size = "small",
    srcs = glob(
        ["*.java"],
        exclude = ["FuseCASTest.java"],
    ) + select({
        ":fuse": ["FuseCASTest.java"],
        "//conditions:default": [],
    }),
    classpath_resources = [
        "//src/test/java/build/buildfarm:configs",
    ],
    test_class = "build.buildfarm.AllTests",
    deps = [
        "//src/main/java/build/buildfarm/common",
        "//src/main/java/build/buildfarm/instance",
        "//src/main/java/build/buildfarm/worker",
        "//src/main/java/build/buildfarm/worker/resources",
        "//src/main/protobuf:build_buildfarm_v1test_buildfarm_java_proto",
        "//src/test/java/build/buildfarm:test_runner",
        "@googleapis//:google_rpc_code_java_proto",
        "@maven//:com_github_jnr_jnr_constants",
        "@maven//:com_github_jnr_jnr_ffi",
        "@maven//:com_github_serceman_jnr_fuse",
        "@maven//:com_google_guava_guava",
        "@maven//:com_google_jimfs_jimfs",
        "@maven//:com_google_protobuf_protobuf_java",
        "@maven//:com_google_truth_truth",
        "@maven//:io_grpc_grpc_api",
        "@maven//:io_grpc_grpc_context",
        "@maven//:io_grpc_grpc_core",
        "@maven//:io_grpc_grpc_protobuf",
        "@maven//:org_mockito_mockito_core",
        "@remote_apis//:build_bazel_remote_execution_v2_remote_execution_java_proto",
    ],
)
