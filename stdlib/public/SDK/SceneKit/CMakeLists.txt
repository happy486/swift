add_swift_library(swiftSceneKit ${SWIFT_SDK_OVERLAY_LIBRARY_BUILD_TYPES} IS_SDK_OVERLAY
  SceneKit.swift.gyb

  SWIFT_COMPILE_FLAGS "${SWIFT_RUNTIME_SWIFT_COMPILE_FLAGS}"
  LINK_FLAGS "${SWIFT_RUNTIME_SWIFT_LINK_FLAGS}"
  TARGET_SDKS OSX IOS IOS_SIMULATOR TVOS TVOS_SIMULATOR WATCHOS WATCHOS_SIMULATOR
  SWIFT_MODULE_DEPENDS_OSX Darwin AppKit CoreData CoreGraphics CoreImage Dispatch Foundation GLKit IOKit ObjectiveC QuartzCore simd XPC # auto-updated
  SWIFT_MODULE_DEPENDS_IOS Darwin CoreGraphics CoreImage Dispatch Foundation GLKit ObjectiveC QuartzCore simd UIKit # auto-updated
  SWIFT_MODULE_DEPENDS_TVOS Darwin CoreGraphics CoreImage Dispatch Foundation GLKit ObjectiveC QuartzCore simd UIKit # auto-updated
  SWIFT_MODULE_DEPENDS_WATCHOS Darwin CoreGraphics Dispatch Foundation ObjectiveC simd # auto-updated
    UIKit # required in some configurations but not found by tool
  FRAMEWORK_DEPENDS_WEAK SceneKit
)
