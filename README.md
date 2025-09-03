# flutter_abi_filters_demo

This project is used to verify the issue of `Flutter 3.35.1` https://github.com/flutter/flutter/issues/174004

# fixed

https://docs.flutter.dev/release/breaking-changes/default-abi-filters-android

```
# kts
android {
    buildTypes {
        release {
            // Clear the automatically set filters.
            ndk.abiFilters.clear()
            // Set your custom filters.
            ndk.abiFilters.addAll(listOf("arm64-v8a", "armeabi-v7a"))
        }
    }
}

# groovy
android {
    buildTypes {
        release {
            // Clear the automatically set filters.
            ndk.abiFilters.clear()
            // Set your custom filters.
            ndk.abiFilters= ["arm64-v8a", "armeabi-v7a"]
        }
    }
}

```