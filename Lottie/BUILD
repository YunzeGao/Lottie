load(":bl_apple_library.bzl", "objc_library")
load("@build_bazel_rules_apple//apple:ios.bzl", "ios_static_framework")

objc_library(
    name = "lottie_library",
    hdrs = glob([
	    "include/Lottie/*.h"
	]),
    srcs = glob([
	    "Lottie/*.h",
	    "Lottie/*.m"
	]),
    copts = [
        "-iquote Lottie/Lottie",
        "-iquote Lottie/include/Lottie",
    ],
    sdk_frameworks = [
    	"UIKit",
    ],
    includes = ["include"],
)

ios_static_framework(
    name = "Lottie",
    deps = [":lottie_library"],
    hdrs = glob(["include/Lottie/*.h"]),
    umbrella_header = "include/Lottie/Lottie.h",
    families = ["iphone", "ipad"],
    minimum_os_version = "11.0",
    minimum_deployment_os_version = "11.0",
)
