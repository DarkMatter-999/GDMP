cc_library(
    name = "gpu_helper",
    srcs = ["gpu_helper.cc"],
    hdrs = ["gpu_helper.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":gpu_resources",
        "//GDMP/framework:image",
        "//GDMP/framework:packet",
        "@godot-cpp//:godot",
    ] + select({
        "//mediapipe/gpu:disable_gpu": [],
        "//conditions:default": [
            "//mediapipe/gpu:gl_calculator_helper",
            "//mediapipe/gpu:gpu_buffer",
            "//mediapipe/gpu:gpu_shared_data_internal",
        ],
    }) + select({
        "//mediapipe:apple": ["//mediapipe/objc:mediapipe_framework_ios"],
        "//conditions:default": [],
    }),
)

cc_library(
    name = "gpu_resources",
    srcs = ["gpu_resources.cc"],
    hdrs = ["gpu_resources.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/gpu:gpu_shared_data_internal",
        "@godot-cpp//:godot",
    ],
)
